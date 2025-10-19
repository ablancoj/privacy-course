# Privacy in machine learning

## Machine learning pipeline

![alt text](figs/ml_pipeline.png)

## Threats

Several studies, such as Shokri et al. (2017), among many others, have shown that trained ML models may leak personal information from the data used to train them.

- Membership inference attacks
- Attribute inference attacks
- Reconstruction attacks

![alt text](figs/neural_network.png)

While we will mostly refer to neural networks and deep learning most of the privacy issues described apply to other models.
Most classification models output the decisions’ confidence.
Other models directly leak private information, such as kNN and SVMs, which include some (or all) training data as part of the model.
DP techniques easily apply to differentiable model training (e.g., SGD).

### Threat model

- Type of access to the model
  - Black-box access → prediction probabilities, logits in DL.
  - White-box access → weights, activations, gradients during training, known architecture.
- Learning architecture
  - Centralized learning → published trained model, API-only access.
  - Federated learning → open to white-box attacks
- Knowledge of data distribution
  - Availability of public data, synthetic data, correlations in attributes, etc.

## MIA

MIAs aim to determine whether a data point was present in the training data used to build a model. 
Given a point in the distribution and a trained model, the attack returns 1 bit of information. 

![alt text](figs/mia.png)

Although this may not at first seem to pose a serious privacy risk, the threat is clear in settings such as health analytics where the distinction between case and control groups could reveal an individual's sensitive conditions.
Successful MIAs open the door to other attacks, such as attribute inference and reconstruction attacks.
They can also be used to detect copyright violations or to measure unlearning success.

*Experiment* (Membership Experiment $Exp^M(\mathcal{A},A,n,\mathcal{D})$).
Let $\mathcal{A}$ be an adversary, $A$ a learning algorithm, $n$ be a positive integer, and $\mathcal{D}$ be a distribution over data points $(x,y)$. The membership experiment proceeds as follows:
   1. Sample $S \sim \mathcal{D}^n$, and let $A_S = A(S).
   2. Choose $b \leftarrow \{0,1\}$ uniformly at random.
   3. Draw $z \sim S$ if $b=0$, or $z \sim D$ if $b=1$.
   4. $Exp^M(\mathcal{A},A,n,\mathcal{D})$ is $1$ if $\mathcal{A}(z, A_S, n, \mathcal{D}) = b$ and 0 otherwise. $\mathcal{A}$ must output either $0$ or $1$. 

*Membership advantage*. The membership advantage of $\mathcal{A}$ is defined as

$$Adv^M(\mathcal{A}, A, n, \mathcal{D}) = 2 \Pr[Exp^M(\mathcal{A}, A, n, \mathcal{D})=1]-1$$

where probabilities are taken over the coin flips of $\mathcal{A}$, the random choices of $S$ and $b$, and the random data point $z \sim S$ or $z \sim D$.

Equivalently, the right-hand side can be expressed as the difference between $\mathcal{A}$'s true and false positive rates

$$ Adv^M = \Pr[\mathcal{A}=0|b=0] - \Pr[\mathcal{A}=0|b=1]$$

where $Adv^M$ is shortcut for $Adv^M(\mathcal{A}, A, n, \mathcal{D})$.

### Connection to overfitting

Overfitting has been shown to predict attacker advantage (Yeom et al. 2018).
In black-box attacks, prediction probabilities (for any classifier) or prediction loss are used to determine membership.
Models, especially when overfit to the training data, display different behavior when encountered with previously seen data.

![alt text](figs/mia_overfitting.png)

![alt text](figs/evo_non_overfit.mp4)

![alt text](figs/evo_overfit.mp4)

![alt text](figs/salem.png)

## Attribute inference attacks

In an attribute inference attack, the adversary uses a machine learning model and incomplete information about a data point to infer missing information.
For example, the adversary is given partial information about an individual's medical record and attempts to infer the individual's genotype by using a model trained on similar medical records.
Can be obtained from successful MIA.

![alt text](figs/aia.png)

## Reconstruction attacks

Reconstruction or model inversion attacks attempt to build the whole training dataset from the information leaked by the trained model.
Can also be obtained from MIAs.
Often use GANs.

![alt text](figs/reconstruction.png)

## Approximate differential privacy

Let $\epsilon$ be a positive real number and $\mathcal{A}$ be a randomized algorithm that takes a dataset as input. Let  $im \mathcal{A}$ denote the image of $\mathcal{A}$. The algorithm $\mathcal{A}$ is said to provide $(\epsilon,\delta)$-differential privacy if, for all datasets $D_1$ and $D_2$ that differ on a single element (i.e., the data of one person), and all subsets $S \subset im \mathcal{A}$:

$$\Pr[\mathcal{A}(D_1) \in S] \le e^{\epsilon}\Pr[\mathcal{A}(D_2) \in S]+\delta $$

where the probability is taken over the randomness used by the algorithm.

  - $\epsilon$ should be close to $0$ and $\delta << 1/|D|$ 
  - Sequential composition: applying mechanisms that are ($\epsilon_i,\delta_i)$-differentially private results in $(\sum \epsilon_i, \sum \delta_i)$-differential privacy.
  - Resistance to post-processing: no processing done on data released by a differentially private mechanism will degrade the privacy guarantee.
  - $(\epsilon,\delta)$-DP is often achieved via the Gaussian mechanism:

$$ \mathcal{M}_{Gauss} = f(x) + \mathcal{M}\left(0, \frac{2\ln(1.25/\delta)(\Delta f)^2}{\epsilon^2} \right) $$

  - Differential privacy bounds the probability of identifying any individual record within a database, parametrized by $\epsilon$.
  - Results of a DP function are unaltered by the presence or absence of any single record.
  - This looks ideal to protect against MIAs in ML.
  - $\epsilon$ closer to 0 provide more privacy at the cost of less data utility.
  - Relaxations to DP attempt to mitigate this.
  - In ML, $(\epsilon,\delta)$-DP has been applied to stochastic gradient descent, together with the moments accountant.


![alt text](figs/dpsgd.png)

Yeom provides a bound for the attacker’s advantage in DPML:

$$Adv \le e^\epsilon - 1$$

$Adv=1$ implies privacy is broken. Therefore, the bound is irrelevant for:

$$ \epsilon \ge \ln{⁡2} \approx 0.7 $$

![alt text](figs/dp_bound.png)

  - DP-SGD introduces several new hyperparameters to optimize: $\sigma$, $\epsilon$, $\delta$, $q=L/N$, $C$, $T$, which are interdependent.
  - To correctly compute the noise to add and not lose additional utility, it should be computed on a per example basis, thus losing most of the benefits of parallelization 
  - Training times increase of 10x—50x.
  - Relaxations of DP make the privacy guarantees even less clear, e.g., the moments accountant.
  - High accuracy loss, especially if choosing adequate budgets.


![alt text](figs/dpfy1.png)
![alt text](figs/dpfy2.png)
![alt text](figs/dpfy3.png)

## Machine unlearning

An unlearning algorithm takes as input a pre-trained model and one or more samples from the train set to unlearn (the "forget set").
From the model, forget set, and retain set, the unlearning algorithm produces an updated model.
An ideal unlearning algorithm produces a model that is indistinguishable from the model trained without the forget set.
MIA advantage used as a metric.

![alt text](figs/unlearning.png)

## Federated learning

Federated learning (FL) is a machine learning setting where many clients (e.g., mobile devices or whole organizations) collaboratively train a model under the orchestration of a central server, while keeping the training data decentralized. 
FL embodies the principles of focused data collection, minimization, separation, and aggregation and can mitigate many of the systemic privacy risks and costs resulting from traditional, centralized machine learning and data science approaches.

![alt text](figs/fl.png)

While FL helps with privacy, it still has some issues to consider:
Privacy issues → White-box access to clients’ contributions.
Security issues → Byzantine, poisoning, adversarial attacks.
Homomorphic encryption, secure multiparty computation, differential privacy at the client level, etc. have been used to tackle some of the privacy issues.
Outlier and anomaly detection mechanisms can be used to detect security attacks.
Some protections against these issues have a negative effect on the other.

![alt text](figs/homo-fl.png)

Secure aggregation protects against a honest-but-curious model manager.
Still, MIAs, AIAs, and reconstruction attacks are still feasible on the aggregated model.
Secure aggregation may prevent the model manager from protecting against security attacks (e.g., byzantine & poisoning attacks).
