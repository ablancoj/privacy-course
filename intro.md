# Privacy engineering course

```{tableofcontents}
```

## Introduction

Modern data processing systems increasingly rely on vast, heterogeneous datasets that can reveal intimate details about individuals’ behavior, preferences, and identities. The General Data Protection Regulation (GDPR) established a new paradigm for safeguarding personal information: data protection by design and by default. This principle requires that privacy considerations be integrated into system architecture and decision-making from the very beginning—not added later as a corrective measure.

Privacy by Design (PbD) entails anticipating and mitigating privacy risks throughout the entire lifecycle of data processing—from collection and storage to analysis, sharing, and deletion. Instead of treating privacy as a compliance box, PbD makes it a fundamental design objective. The key mechanism to achieve this is the Data Protection Impact Assessment (DPIA), a structured risk analysis that identifies what personal data are processed, for what purposes, and under which security and governance conditions. The DPIA evaluates potential threats (e.g., unauthorized access, misuse, or re-identification) by estimating their likelihood and impact, then defines mitigation strategies proportional to the risk.

International guidelines from bodies like the AEPD, ENISA, and NIST emphasize that risk must be evaluated not only by technical factors but also by contextual ones—such as the sensitivity of the data, the vulnerability of the subjects (e.g., minors), and the intended data uses. Privacy by design, therefore, is both a technical and ethical framework: it seeks to preserve individuals’ autonomy and dignity by embedding privacy into the structure of information systems.

PbD principles can be grouped into eight complementary strategies:

Minimize: Collect and retain only the data strictly necessary for the purpose.

Hide: Secure data through encryption and limit access to authorized parties.

Separate: Avoid unnecessary data linkage; process data in distributed or federated form when possible.

Aggregate: Work with the least granular data needed for a given analysis.

Inform: Ensure transparency about data use in clear, accessible language.

Control: Provide mechanisms for individuals to exercise their data rights.

Enforce: Align technical controls and organizational practices with privacy policies.

Demonstrate: Keep documentation and logs that show compliance and accountability.

From these principles emerges the entire field of privacy engineering, which translates legal obligations into concrete technical mechanisms.

2. Privacy-Enhancing Techniques (PETs)

Privacy-Enhancing Techniques are technological enablers of privacy by design. They allow organizations to provide core digital functions—authentication, communication, data analysis—while revealing minimal information about users. Most PETs are rooted in cryptography, which ensures confidentiality, integrity, and accountability without compromising anonymity.

Among these techniques, digital signatures guarantee authenticity but may expose identities. To address this, several privacy-preserving variants exist:

Blind signatures enable a party to sign a message without reading it, allowing anonymous yet verifiable transactions (as in early e-cash and e-voting systems).

Group signatures allow any member of a group to sign on behalf of all, ensuring anonymity within the group while enabling accountability through a trusted manager.

Attribute-based signatures prove possession of a property (e.g., being over 18 or a licensed physician) without revealing identity.

Zero-Knowledge Proofs (ZKPs) let someone prove that they know a secret or satisfy a condition without disclosing any details—key for authentication and blockchain privacy protocols.

Beyond authentication, PETs also support anonymous credentials and pseudonymization, enabling continuity of interaction without persistent identification. In communication systems, mix networks, onion routing, and the Tor network protect metadata, hiding who communicates with whom. More advanced approaches, like homomorphic encryption, secure multiparty computation (SMPC), and trusted execution environments (TEEs), allow computation on encrypted or distributed data without exposing its contents.

Together, these mechanisms operationalize the principles of minimization, hiding, and separation—forming the technological foundation for privacy-respecting systems.

3. Protecting Structured Data: From Tables to Queries

Structured data, such as that collected in surveys or administrative databases, can often be transformed into tabular outputs for publication or analysis. Even aggregated tables, however, can leak sensitive information if small groups or unique combinations of attributes are disclosed. To mitigate this, statistical disclosure control (SDC) techniques modify or withhold risky cells.

Common SDC methods include:

Cell suppression, where small or sensitive counts are omitted, often with complementary suppression to prevent deduction from totals.

Controlled rounding or adjustment, which slightly modifies numerical values to obscure exact counts while preserving overall consistency.

Interval reporting, which replaces exact values with ranges (e.g., “between 3 and 7 cases”).

Noise addition, which introduces random perturbations calibrated to protect individual contributions.

The objective is to balance disclosure risk—the probability that an individual can be inferred—with information loss—the degradation of data utility. Tabular data protection demonstrates that even aggregate statistics require careful anonymization to maintain confidentiality.

When users can query data directly, as in queryable databases, new risks arise. Repeated or overlapping queries can reconstruct individual information. To prevent this, systems employ:

Query restriction, refusing queries that affect too few records.

Query camouflage, returning generalized intervals instead of precise numbers.

Query perturbation, adding noise to query results.

The last approach leads to differential privacy (DP)—a formal framework ensuring that the inclusion or exclusion of any single individual’s data has negligible impact on the output. DP quantifies privacy through a parameter ε (epsilon): smaller ε means stronger protection but greater noise. Differential privacy has become a global standard, applied in government censuses and major technology platforms. Its conceptual ancestor, randomized response, introduced in the 1960s, uses randomness in survey answers to protect individuals while allowing valid statistical estimates—an intuitive early form of privacy-preserving data collection.

4. Microdata Anonymization

When individual-level data must be shared for research or statistical purposes, microdata anonymization transforms quasi-identifiers to prevent re-identification. The foundational model, k-anonymity, ensures that each record is indistinguishable from at least k–1 others. Extensions like l-diversity and t-closeness strengthen protection by maintaining diversity and distributional similarity in sensitive attributes, thus limiting attribute disclosure.

Anonymization methods can be:

Non-perturbative, preserving data correctness but reducing precision through generalization and suppression.

Perturbative, introducing controlled randomness (e.g., data swapping, noise addition, or synthetic data generation).

Risk–utility analysis guides the process: increasing privacy (higher k or tighter t) usually decreases analytical value, and the optimal balance depends on the use context. Microdata anonymization remains essential in health, social, and economic research, bridging classical statistical methods and modern privacy frameworks like differential privacy.

5. Privacy in Unstructured Data

Unstructured data—images, text, video, location traces, genomic sequences—poses unique challenges because identifiers are embedded in complex content rather than explicit fields.

For images, privacy risks arise from both content (faces, objects, backgrounds) and metadata (timestamps, GPS, device signatures). Common protections include blurring, pixelation, and masking, complemented by metadata cleaning. Newer methods use adversarial perturbations that fool face-recognition systems without perceptibly altering the image. In medicine, anonymization focuses on DICOM metadata removal and obscuring embedded text rather than modifying image content.

For textual data, privacy-enhancing NLP tools automatically detect and mask names, dates, and other sensitive terms using Named Entity Recognition (NER). Redaction can be performed by deletion or generalization; however, excessive sanitization may compromise semantic meaning. Synthetic text generation using large language models can provide an alternative by rewriting sensitive passages without reproducing original identifiers.

Location and genomic data pose especially high re-identification risks, as they are inherently unique. Location privacy is achieved through spatial and temporal generalization or the addition of noise, while genetic data typically relies on controlled access rather than anonymization, since true de-identification is infeasible.

Unstructured data anonymization thus combines content editing, metadata sanitization, and increasingly AI-assisted generation to balance privacy and utility in multimedia and textual information.

6. Privacy in Machine Learning

Machine learning systems amplify privacy challenges by processing vast, diverse datasets to extract predictive patterns. These models can unintentionally memorize or reveal sensitive data, creating new categories of attacks:

Membership inference attacks, which determine whether a given record was part of the training set.

Attribute inference, which deduces hidden features about individuals.

Model inversion and reconstruction, which regenerate approximate training examples.

Data poisoning, where malicious inputs alter the model or cause targeted leaks.

Mitigations span multiple layers:

Differentially Private Stochastic Gradient Descent (DP-SGD) injects noise during training to guarantee that model parameters reveal little about any single data point.

Federated learning keeps data local and aggregates updates across devices, often combined with secure aggregation and DP to prevent server-side inference.

Cryptographic computation (SMPC, homomorphic encryption) enables joint training or inference across institutions without sharing raw data.

Regularization and access control reduce overfitting and limit adversarial probing.

These approaches operationalize privacy by design in AI: models are trained and deployed under quantifiable privacy constraints rather than relying on post hoc anonymization.

7. Machine Unlearning and the Right to Be Forgotten

Privacy protection does not end when training concludes. Under the GDPR’s right to erasure, individuals may request that their data—and its influence—be removed from systems. Machine unlearning addresses this requirement by designing models capable of “forgetting” specific training samples efficiently, without full retraining.

Unlearning methods include:

Selective retraining, recomputing only affected components (e.g., trees in ensembles).

Influence-based rollback, estimating and reversing each record’s contribution to model parameters.

Gradient ascent unlearning, which counteracts the learned effect of deleted data.

Partitioned or modular training, designing models that can forget data partitions by design.

Certified unlearning frameworks aim to provide verifiable guarantees that a model behaves as if specific data were never used, bridging AI practice with legal accountability. This capability embodies the ultimate stage of privacy by design—systems that can both learn and forget responsibly.

8. Conclusion: The Continuum of Privacy by Design

Across these domains—structured, unstructured, and machine-learned data—the core challenge remains constant: balancing information utility with individual privacy. From risk assessment and anonymization to differential privacy and unlearning, each technique represents a step along a continuum from prevention to accountability.

Privacy by design is thus not a single technology but an ecosystem of principles, methods, and tools. It integrates cryptography, statistics, and artificial intelligence into a coherent discipline: privacy engineering. As data-driven systems grow more pervasive and autonomous, this discipline ensures that technological innovation remains aligned with ethical responsibility and human dignity.