# Privacy by design

Privacy by design is a fundamental requirement of the GDPR that calls for integrating privacy and data protection considerations into every stage of the design and development process. Rather than treating privacy as an afterthought, systems and services that collect or process personal data must be built from the ground up with privacy in mind. This approach applies to all types of data-driven environments, including web platforms, mobile applications, wearable technologies, and research infrastructures.

A central component of privacy by design is the Data Protection Impact Assessment (DPIA), which functions as a structured risk assessment. It identifies what personal data is collected, how it is stored and processed, the parties that have access to it, and the potential risks to individuals’ rights and freedoms. These assessments should be conducted not only at the start of a project but also throughout its life cycle, as systems evolve and new risks appear. Guidelines for conducting DPIAs are provided by organizations such as the Spanish Data Protection Agency (AEPD), ENISA, and NIST. Risk factors depend on the type of processing (for example, profiling or monitoring), the sensitivity of the data (such as health, biometric, or financial information), the retention period, and the vulnerability of the data subjects. Children, for instance, require special protection because they cannot give valid consent.

Risk analysis combines the likelihood of a threat occurring with the potential impact it might have. High-risk scenarios typically involve sensitive data, poor access control, or the possibility of reidentifying individuals from anonymized datasets. Examples of real-world applications of this analysis include open data initiatives where authorities weigh the social benefits of publishing information against the privacy risks. For example, releasing data on emergency calls may have high public value but also poses significant reidentification risks, making it unsuitable for full disclosure without strong anonymization measures.

The concept of privacy by design can be organized into eight core strategies. Four of them are data-oriented:
1. Minimize – Collect only the data necessary for the intended purpose and avoid excessive data collection. Processing can be performed locally when possible to reduce the transmission of personal data.
2. Hide – Protect data through encryption, access control, and secure communication. Only authorized individuals should be able to view or manipulate personal data.
3. Separate – Keep different categories of data apart to avoid unnecessary linkages that could lead to identification. Distribute processing across systems instead of centralizing it, using approaches such as federated learning.
4. Aggregate – Whenever feasible, work with aggregated or anonymized data rather than individual records. Reducing the level of detail lowers privacy risks while still allowing useful analysis
The remaining four are process-oriented strategies that address how organizations manage data and interact with individuals:
5. Inform – Ensure transparency by clearly explaining how data is collected, processed, and used, using accessible language rather than legal jargon.
6. Control – Provide individuals with effective means to exercise their data protection rights, such as accessing, correcting, or deleting their data.
7. Enforce – Guarantee that internal practices and technical safeguards comply with established privacy policies and legal requirements. Implement access control and monitoring to prevent unauthorized use.
8. Demonstrate – Maintain comprehensive documentation and logs to prove compliance and support accountability, especially in the event of audits or incidents.

Together, these principles ensure that data protection is embedded into both the technical architecture and the organizational culture of any system handling personal data. They promote proactive, transparent, and responsible data management that not only meets regulatory requirements but also strengthens user trust.

:::{grid} 1 1 2 3

:::{card} Data Strategies
- Minimize
- Hide
- Aggregate
- Separate
:::

:::{card} Process Strategies
- Inform
- Control
- Enforce
- Demonstrate
:::

:::

## Risk assessment

When performing a risk assessment of a system that processes personal data, the first step is to describe the personal data processing activities. This includes the collection of data (for example via user inputs, sensors, third-party feeds), storage (databases, files, cloud services), analysis (data mining, profiling, predictive models) and exchange (sharing with other internal or external systems, APIs, third parties). Next, you should identify the likelihood of privacy threats: how likely is it that personal data may be linked, re-identified, or disclosed inadvertently or maliciously? For example, does the system combine identifiers and quasi-identifiers making re-identification feasible? Then you assess the impact of privacy threats – what are the consequences if a breach or misuse occurs? This might include economic costs (fines, remediation, business loss), reputational damage, legal liabilities, or harm to individuals (identity theft, discrimination). Once you have both likelihood and impact, you compute risk = Likelihood × Impact as a quantitative or semi-quantitative measure, which helps prioritise risk areas. Finally, you propose countermeasures: technical, organisational or procedural measures to reduce both the likelihood and/or impact of the identified threats (for example encryption, access controls, anonymization, limiting retention, staff training).

### AEPD



### Seattle example


Model Open Data Benefit-Risk Analysis In the open data context, considering the risks of the dataset is merely one part of a balanced value equation; decision-makers must also take account of the project’s benefits in order to make a final determination about whether to proceed with publishing the dataset openly.22 For the purposes of this report, FPF developed this Model Analysis, which is based on risk assessment and de-identification frameworks developed by the National Institute of Standards and Technology and also builds on parallel efforts by researchers at the University of Washington, the Berkman Klein Center, and the City of San Francisco to develop robust risk-based frameworks for government data releases.23 This Model Analysis provides a structure for vetting potential open datasets in five steps: Step 1: Evaluate the Information the Dataset Contains. This step includes identifying whether there are direct or indirect identifiers, sensitive attributes, or information that is difficult to de-identify present in the dataset; assessing how linkable the information might be to other datasets; and considering the context in which the data was obtained. Step 2: Evaluate the Benefits Associated with Releasing the Dataset. This step considers the potential benefits and users of the dataset, and assesses the magnitude of the potential benefits against the likelihood of their occurring. Step 3: Evaluate the Risks Associated with Releasing the Dataset. This step considers the potential privacy risks and negative users of the dataset, and assesses the magnitude of the potential risks against the likelihood of their occurring. Step 4: Weigh the Benefits against the Risks of Releasing the Dataset. This step combines the overall scores from steps 2 and 3 to determine an appropriate method for releasing (or not releasing) the dataset. Recommendations include releasing as open data, in a limited access environment, or not publishing at the current time. This section also overviews common methods for reducing re-identification risk in terms of their privacy-protective, utility, and operational impacts. Step 5: Evaluate Countervailing Factors. This step provides a final opportunity to document any countervailing factors that might justify releasing a dataset openly regardless of its privacy risk, such as when there is a compelling public interest in the information.



### LINDDUN


## PbD Strategies


::::{grid} 1 1 2 4

:::{card}
Minimize
^^^
Collect and retain only the data strictly necessary for the purpose.
:::

:::{card}
Hide
^^^
Secure data through encryption and limit access to authorized parties.
:::

:::{card}
Separate
^^^
Avoid unnecessary data linkage; process data in distributed or federated form when possible.
:::

:::{card}
Aggregate
^^^
Work with the least granular data needed for a given analysis.
:::

:::{card}
Inform
^^^
Ensure transparency about data use in clear, accessible language.
:::

:::{card}
Control
^^^
Provide mechanisms for individuals to exercise their data rights.
:::

:::{card}
Enforce
^^^
Align technical controls and organizational practices with privacy policies.
:::

:::{card}
Demonstrate
^^^
Keep documentation and logs that show compliance and accountability.
:::

::::

## Data strategies

### Minimize

The amount of personal data processed should be restricted to the minimum necessary. By avoiding collection of unnecessary data, the system limits potential privacy impacts. Key questions include: Is the data processing proportional to the purpose? Are there less-invasive means to achieve the same goal? Typical design patterns supporting minimisation include “select before you collect,” anonymisation, or use of pseudonyms.

Minimise
The goal of this strategy is to collect and process the least amount of data possible,
thus averting the processing of unnecessary data and limiting possible impacts on
[18]
privacy. This may be achieved by collecting data from fewer subjects (reducing the
population size) or less data from subjects (reducing the volume of collected
information), for which the following tactics may be used:
• Select: select only the sample of relevant individuals and the attributes
required, with a conservative approach when establishing the selection criteria
and processing only the data that satisfy the selection criteria (white list).
• Exclude: is the reverse of the earlier approach and consists of excluding
beforehand subjects and attributes that are irrelevant to the processing (black
list). In this case, an open attitude must be adopted, excluding as much
information as possible unless their inclusion can be justified as being
absolutely necessary for the intended goal.
• Strip: partially eliminate personal data as soon as they cease to be necessary,
which requires establishing beforehand the storage period of each of the
collected data, and to establish automatic deleting mechanisms when said
period is over. In case the data are part of a record that has more information
than is necessary, the value of the unnecessary fields can be modified to a
prefixed default value.
• Destroy: completely delete personal data as soon as they cease to be relevant,
ensuring that it is impossible to recover both the data and any backup copies.
It is also important to remember that only strictly necessary data must be
communicated and shared, and in case of processing where new personal information is
extrapolated, generated data that is not necessary to achieve the intended purpose must
also be deleted.

Minimise Limit the processing of personal data as much as possible. TACTICS: select, exclude, strip and destroy Anonymisation Pseudonymisation Block correlation in federated identity management systems

### Hide

Any personal data and their interrelationships should be hidden from plain view (reflecting the information security dimension). This strategy seeks unlinkability and unobservability: to ensure that personal data cannot be easily abused because they are concealed, encrypted or otherwise protected. Design patterns include encryption (data at rest or in transit), mixing networks to hide traffic patterns, attribute-based credentials, pseudonyms and anonymisation.

This strategy focuses on limiting data observability by establishing necessary means
to guarantee the protection of confidentiality and unlinkability. The following tactics are
used to implement this strategy:
• Restrict: restrict access to personal data by setting limits through an access
control policy that implements a “need to know" principle both in space
(details and type of data accessed) and in time (processing stages).
• Obfuscate: make personal data unintelligible for those who are not authorised
to consult it, using encryption techniques and hashing, both for storage
operations as well as information transmission.
• Dissociate: eliminate the link between datasets that should be kept
independent, as well as the identification attributes of data records to avert
correlations between them, with special attention to metadata.
• Mix: Group together information on various subjects using generalisation and
suppression techniques[33]
to avoid correlations.

Hide Avoid making personal data public or known TACTICS: restrict, obfuscate, dissociate and mix) Encryption Mix networks Attribute Based Credentials

### Separate

Personal data should be processed in a distributed fashion, and data from separate sources should be stored or processed in distinct compartments where possible. The underlying rationale is that by separating storage or processing of data that belong to the same individual, you reduce the ability to build comprehensive profiles. Examples include storing different data types in separate databases, processing data locally rather than centrally, splitting database tables, and using federated learning or blockchain‐based approaches.

The goal of this strategy is to avoid, or at least minimise the risk that while processing, within one entity, different personal data of the same individual that are used in
independent processes, can be combined to create a complete profile of the data
subject. For this, it is necessary to maintain independent processing contexts that make
it difficult to correlate datasets that should be unlinked. The following tactics help to
implement a separation strategy:
• Isolate: collect and store personal data in different databases or applications
that are independent, either logically or are executed on different physical
systems, adopting additional measures to guarantee unlinkability, such as the
programmed deletion of database indexes.
• Distribute: Spread out the collection and processing of different subsets of
personal data corresponding to different types of processing over
management and handling units that are physically independent within the
system, and use different systems and applications to implement
decentralised and distributed architectures that process the information
locally whenever possible, instead of using centralised solutions with unified
access which may depend on a single control unit

Keep personal datasets separate. TACTICS: isolate and distribute Anonymous black lists Homomorphic encryption Physical and logical separation


### Aggregate

Personal data should be processed at the highest level of aggregation and with the least detail necessary for the purpose. When data refer only to groups rather than to individuals, the sensitivity is reduced. Examples of supporting design patterns include k-anonymity, temporal aggregation (for example in smart metering), location coarsening in location-based services, and differential privacy.

The idea behind this strategy is to limit the details of the processed personal data as
much as possible. While the ‘minimise’ strategy makes a previous selection of the data to
be collected, this strategy focuses on the degree of detail in which the data are processed
and on their aggregation by using three tactics:
• Summarise: generalise the values of the attributes using value ranges or
intervals, instead of a concrete field value.
• Group: aggregate information of a group of records into categories instead of
using the detailed information on each of the subjects that belong to the group,
by using average or general values.
• Perturb: use approximate values or modify the real data using some type of
random noise instead of employing the exact value of the personal data.
For each data processing, it is necessary to study how the level of detail of the entered
data affects the result, and what is the degree of precision necessary for effective
processing. Especially, the length of time after the data was collected may affect their
relevance, which is why it is useful to periodically review the stored information and
apply these strategies [34]
. 

Limit the level of detail used in personal data processing as much as possible. TACTICS: summarise, group and perturb Time-based group K-anonymity Added noise measurement obfuscation Dynamic location granularity Differential privacy


## Process strategies

### Inform

Data subjects should be clearly informed about what information is being processed, for what purpose, by which means, and how it is protected. Transparency means providing clear documentation, notices, and informing subjects if data are shared with third parties. Also informing them about their access rights and how to exercise them. Design patterns include the Platform for Privacy Preferences (P3P), transparency enhancing tools.

This strategy implements the transparency goals and principles established by the
Regulation and seeks to make data subjects fully aware of the processing of their data in
a timely manner. Whenever processing is carried out, the subjects whose data is
processed must be aware of what is being processed, to what end and which third partiesare given this information, in addition to all that is laid down in Articles 13 [35] and 14 [36] of
the GDPR. Transparency with regard to this information is a basic requirement of privacy
as it allows data subjects to make informed decisions on the processing and accordingly
provide free, specific, informed and unambiguous consent. Any modification in
processing regarding previously provided information must be communicated, including
possible security breaches that may significantly affect the freedoms and liberties of data
subjects. This strategy is based on the existence of privacy clauses that facilitate the
global communication of this information to the data subjects, along with the use of the
following tactics:
• Supply: provide data subjects with all the information required by the GDPR
on what personal data is processed, how it is processed and why, by identifying
the motive and goal. Details on data storage periods must be provided, as well
as on the sharing of this data with third parties. Along with this information,
which must be accessible and continually provided in order to promote an
authentic transparency, it must also indicate who can be contacted by the data
subjects and how, in order to ask questions on their privacy as well as their
rights with regard to personal data protection.
• Explain: provide information on data processing in a concise, transparent,
intelligible and easily accessible fashion in clear and simple language. To avoid
dense, complex and unwieldy information policies, it is worth adopting a
layered approach which first provides basic information at the same time and
within the same data collection medium and makes additional detailed
information available at a second level [37]
.
• Notify: inform data subjects of the processing when the data are not derived
directly from them, at the time these have been obtained and within a
maximum of one month, or if they are going to be used for communication with
them, in the first message. Subjects must also be informed if their data is going
to be transferred to third parties. Mechanisms to notify subjects of security
breaches that may have happened and may pose a serious risk to their
freedoms and rights must also be implemented, using clear and simple
language to describe the nature of the breach.
Considering that data collection procedures are varied, the means of notification must
be adapted to the circumstances of each method used including, additionally, the
possible use of standardised icons that offer an overall view of the anticipated
processing. 

Keep data subjects informed of the nature and conditions of processing. TACTICS: supply, explain and notify Security breach notifications Dynamic visualisation of privacy policy Privacy icons Ambient notices

### Control

Subjects should be given agency over the processing of their personal data, this ties to individual rights. Informing alone is insufficient unless the subject has some control, and control is impossible without being informed. Control includes enabling subjects to view, update, or delete their data; control interfaces should be easy to use. Design patterns include user-centric identity management, end-to-end encryption to give users control, intervenability.

This strategy is closed linked to the ‘inform’ strategy and it seeks to provide subjects
with control over the collection, processing, use and transfer of their personal data by implementing mechanisms that allow them to exercise their rights of access to,
rectification, erasure, objection, portability and restricting their data and its processing,
as well as the right to give and withdraw consent or modify privacy options in
applications and services. To implement these mechanisms, the following tactics are
used:
• Consent: acquire the consent of data subjects, in cases without any other basis
of legitimacy, and which must be given unambiguously, by demonstrating
either a clear affirmative action which must be explicit in certain situations
such as the processing of sensitive data, the adopting of certain automated
decisions or in international transfers. Besides, the subject must be able to
withdraw their consent at any time, by guaranteed mechanisms and
procedures that make it as easy to withdraw consent as it is to give it.
• Alert: to provide real-time notification to the user when personal data is being
collected, even when general information on the legal basis of the processing
has been provided or even when the subject has already given their consent.
• Choose: to provide granular functionality [38] of applications and services,
especially when it comes to basic functionality, without it being contingent on
the user’s consent to process personal data that is not required for execution.
• Update: implement mechanism that make it easy for users to or even lets them
directly make revisions, updates and rectifications of the provided data for a
specific processing, so that they are accurate and reflect reality.
• Retract: provide mechanisms for users to withdraw or ask for the deletion of
their personal data provided to a controller for processing.
Technological advances that make it possible to continuously collect data also makes
it possible for data to be easily managed by the data subjects through the
implementation of privacy platforms where they can access, update, cancel and modify
the selected privacy settings. These functions must be accounted for when designing an
application. 

Provide data subjects with effective control over their personal data. TACTICS: consent, alert, choose, update, retract Privacy dashboard Active broadcast of presence Credential selection Informed consent


### Enforce

A privacy policy compatible with legal requirements should be in place and must be enforced. This strategy ensures that the system respects privacy commitments. Technical protection mechanisms should exist to prevent policy violations, and governance structures must enforce the policy. Design patterns include access control, privacy rights management (a form of DRM for personal data).

This strategy ensures that personal data processing is compatible with and respects
the legal requirements and duties imposed by regulations. For this, it is necessary to
define a privacy framework and an administrative structure that includes a data
protection policy supported by the senior levels of management, as well as the roles and
responsibilities that are entrusted with its compliance. Privacy culture must be an
essential part of the organisation and all members must be participants. The following
tactics may help to achieve this:
• Create: Specify a data protection policy that reflects internally the privacy
clauses that are communicated to data subjects. The necessary structures
must be created, and resources assigned to support this policy and ensure that
the organisation’s processing activities respect and comply with data
protection regulations. A training and awareness plan must also be developed
for all members that seeks to ensure a committed and responsible attitude as
part of accountability.
• Maintain: to support the policy defined by establishing procedures and
implementing the necessary technical and organisational measures. The
existence of effective mechanisms and procedures must be reviewed in order
to guarantee the exercise of rights, the handling and notifying of security
incidents, adjusting possible processing activities to legal requirements and
providing proof of compliance with the obligations imposed by regulations.
• Uphold: to ensure the compliance, effectiveness and efficiency of the privacy
policy and the procedures, measures and controls implemented so that they
account for all processing activities carried out and for the day to day activities
of the organisation.
The figure of the Data Protection Officer plays an essential role in implementing this
strategy, by assessing the controller and supervising the compliance with data
protection regulations within the organisation. Implementing privacy management
models such as that recently proposed by the ISO/IEC 27701:2019 [39] standard is also
effective. It lists the requirements and provides directions for establishing,
implementing, maintaining and continually improving a Privacy Information
Management System (PIMS). 

Respect and promote the fulfilment of the obligations set by current regulations and the data protection policy itself. TACTICS: create, maintain, uphold Privacy impact assessment in federated identity management solutions Access control. Obligation management Adherence to policies




### Demonstrate

The organisation (data controller) must be able to demonstrate compliance with the privacy policy and applicable legal requirements – this entails accountability. It goes beyond enforcement: not only must privacy be enforced, but the organisation must show demonstrably that it is being enforced. Design patterns include logging, auditing, privacy-management systems.

This strategy goes one step further than the earlier strategy and its goal is that in
accordance with Article 24 of the GDPR [40]
, the data controller must be able to
demonstrate to data subjects as well the supervisory authorities that the applicable data
protection policy is being adhered to, in addition to other legal requirements and
obligations imposed by the Regulation. From a practical point of view, this implements
the accountability demanded by the Regulation, based on a critical, continuous and
traceable self-analysis of all decisions on data processing and ensuring authentic
management of personal data within the organisation. The following tactics are used to
carry out this strategy in order to ensure and demonstrate that the processing is in
accordance with the Regulation:
• Record: document each and every decision taken even when they contradict
each other, identifying who took the decision, when and why.
• Audit: carry out a systematic, independent and documented review of the
degree of compliance with the data protection policy.
• Report: document audit results and any other incident regarding personal
data processing operations and make them available to the supervisory
authorities whenever required. In case of new data processing and if the result
of the data protection impact evaluation shows that processing involves a high
degree of risk to the rights and freedoms of the data subjects if the controller
does not adopt measures to mitigate it, perform the prior consultation referred
to in Article 36 [41] of the GDPR.
Performing a risk analysis and when applicable, a data protection impact assessment
together with the documentation on decisions taken with regard to the results, is a good
beginning to establish the privacy requirements that must be implemented in
applications and systems as part of privacy by design, as well as to fully document how
personal data is processed, and follow the principle of accountability. Other resources
for demonstrating the controller’s fulfilment of their obligations is their adherence to
codes of conduct and certifications as optional instruments for implementing this
strategy.

To be able to demonstrate that data processing is respectful of privacy. TACTICS: record, audit and report. Audit Logs



# Privacy by Design

## Introduction

The previous chapter outlined the ethical, legal, and technical foundations of privacy and data protection, culminating in the regulatory framework of the GDPR. This chapter continues from that point by examining one of the key operational requirements emerging from the GDPR and from contemporary best practices in privacy engineering: **privacy by design**.

Privacy by design embodies a simple but powerful idea: privacy should not be an afterthought. It must be embedded into every phase of the system or research lifecycle—from the moment a project is conceived, through design and implementation, and continuing throughout operation, maintenance and eventual decommissioning. This is not merely a technical requirement but a shift in organizational culture and responsibility. It demands that the protection of personal data be treated as a primary design goal, rather than something to address only when problems arise.

In practice, privacy by design connects high-level values such as human dignity, autonomy and fairness with the concrete structures of information systems. It bridges ethics, regulation and engineering, making privacy a discipline that begins long before any code is written.

## Why Privacy Must Be Designed from the Start

The GDPR underscores that organizations collecting or processing personal data must take appropriate measures to safeguard those data. Importantly, these measures cannot be retrofitted. The design of a system determines what data are collected, how those data flow through different components, how they are stored, who can access them, and how long they are retained. Once a system is deployed, changes to its architecture or data collection logic can be extremely costly or technically infeasible.

This is especially clear in contemporary data-driven services. Many systems rely on continuous data collection, often through mobile devices, wearables, sensors, telehealth platforms or web-based services. If such systems are designed without attention to privacy, they may collect far more data than necessary, store them in insecure environments, or combine datasets in ways that increase the risk of re-identification. Considering privacy only after deployment is neither efficient nor compliant with regulatory standards.

Privacy by design therefore requires that teams ask early questions: What data are actually needed? How will they be protected? What risks could arise? How would a breach affect individuals? These questions shape not just the technical architecture but also the organizational processes surrounding it.

## The Software and Research Lifecycle

A typical development lifecycle includes phases such as initial planning, requirements elicitation, analysis, design, implementation, testing, deployment and maintenance. Privacy by design maps directly onto this lifecycle by requiring that privacy considerations appear alongside functional and technical requirements. Instead of treating privacy as a “non-functional” requirement addressed late in the process, it becomes part of the core definition of what the system must achieve.

In the planning phase, teams must articulate the purpose of their system or study and determine whether personal data are genuinely needed. During requirements gathering, they must determine what data are strictly necessary to fulfill those purposes and what constraints follow from regulation or internal policy. In the design phase, they must outline data flows, storage mechanisms, access control models, anonymization or pseudonymization strategies, and interfaces through which data subjects may exercise their rights.

Privacy must also be considered iteratively. As systems evolve, new features or integrations may introduce risks not previously foreseen. Maintenance therefore includes periodically revisiting privacy assessments, updating documentation, reviewing access logs and adjusting protections as technologies or organizational needs change.

## The Privacy Risk Assessment

A central tool in privacy by design is the **privacy risk assessment**, sometimes referred to as a Data Protection Impact Assessment (DPIA) under the GDPR. Not every project requires a formal DPIA, but any system handling personal data should undergo a structured evaluation of potential privacy risks.

A privacy risk assessment typically begins with understanding the context. What types of personal data will be collected? Are they direct identifiers such as names or identification numbers, or indirect identifiers such as dates, locations or demographic attributes? Will sensitive data—such as health, biometric or political information—be involved? Are data collected passively, derived from other sources or shared with third parties?

The assessment then considers how these data are stored and transmitted. For example, if data reside on a server, how secure is that server? Who has access to it? Are logging mechanisms in place? Are backups encrypted? What vulnerabilities might exist?

Evaluating risks involves examining both **likelihood** and **impact**. Likelihood refers to how probable a breach or misuse might be, given the system’s structure and the threat landscape. Impact refers to the harm that may occur if a breach takes place. Low-impact events might involve disclosure of trivial or non-sensitive information. High-impact events might expose medical conditions, financial details or locations of vulnerable individuals, potentially causing discrimination, economic loss, social stigma or threats to personal safety.

Once likelihood and impact are evaluated, they are combined into an overall risk level. High-risk scenarios may require substantial mitigation, such as encryption, access restrictions or even a decision not to collect or publish certain data. Moderate risks might be addressable through techniques like anonymization, generalization or limiting precision. Low risks may simply require good documentation and minimal data collection.

The privacy assessment guides design decisions and serves as a living document throughout the system’s lifecycle. It helps organizations justify their choices to supervisory authorities and demonstrates accountability and due diligence.

## Lessons from Open Data Initiatives

A practical illustration of privacy risk assessment comes from open data programs such as those conducted by municipal governments. Before releasing datasets, authorities must evaluate not only the benefits of public access but also the risks of re-identifying individuals.

For example, emergency call data may include location information, timestamps and details about health or safety incidents. Even without names, such data can be highly identifying when combined with public knowledge about events or geographic uniqueness. In such cases, the risks may outweigh the public benefits, leading authorities to decide against publication.

Other datasets, such as building permits or aggregated demographic data, may be assessed as high risk but offering substantial public value. Here, additional screening—such as removing precise locations, generalizing timestamps or excluding rare categories—can reduce risk to an acceptable level.

These examples illustrate the practical workflow of privacy by design: assess context, evaluate risk, balance benefits and harms, and apply countermeasures proportionate to the risk.

:::{admonition} [Seattle Model Open Data Benefit-Risk Analysis](https://fpf.org/wp-content/uploads/2018/01/FPF-Open-Data-Risk-Assessment-for-City-of-Seattle.pdf) 
In the open data context, considering the risks of the dataset is merely one part of a balanced value equation; decision-makers must also take account of the project’s benefits in order to make a final determination about whether to proceed with publishing the dataset openly. For the purposes of this report, FPF developed this Model Analysis, which is based on risk assessment and de-identification frameworks developed by the National Institute of Standards and Technology and also builds on parallel efforts by researchers at the University of Washington, the Berkman Klein Center, and the City of San Francisco to develop robust risk-based frameworks for government data releases.

This Model Analysis provides a structure for vetting potential open datasets in five steps: 
    1. Evaluate the Information the Dataset Contains. This step includes identifying whether there are direct or indirect identifiers, sensitive attributes, or information that is difficult to de-identify present in the dataset; assessing how linkable the information might be to other datasets; and considering the context in which the data was obtained. 
    2. Evaluate the Benefits Associated with Releasing the Dataset. This step considers the potential benefits and users of the dataset, and assesses the magnitude of the potential benefits against the likelihood of their occurring. 
    3. Evaluate the Risks Associated with Releasing the Dataset. This step considers the potential privacy risks and negative users of the dataset, and assesses the magnitude of the potential risks against the likelihood of their occurring. 
    4. Weigh the Benefits against the Risks of Releasing the Dataset. This step combines the overall scores from steps 2 and 3 to determine an appropriate method for releasing (or not releasing) the dataset. Recommendations include releasing as open data, in a limited access environment, or not publishing at the current time. This section also overviews common methods for reducing re-identification risk in terms of their privacy-protective, utility, and operational impacts. 
    5. Evaluate Countervailing Factors. This step provides a final opportunity to document any countervailing factors that might justify releasing a dataset openly regardless of its privacy risk, such as when there is a compelling public interest in the information.
:::

## Privacy by Design Strategies

To support privacy by design, several public bodies and research groups have articulated general strategies and associated design patterns. A widely adopted framework organizes these into **eight strategies**, of which the first four focus on data processing and the latter four on organizational processes.

### Minimize

The aim of minimization is simple: collect and process as little personal data as possible. Only those data necessary to perform a given task or offer a service should be gathered. Minimization can be achieved by reducing the number of data subjects, reducing the number of attributes collected, or reducing the precision or frequency of collection.

Device-side filtering is one example of minimization. A mobile device may locally decide which data are necessary before transmitting anything to a server. Another common pattern is anonymization, which seeks to irreversibly remove identifying information, though its effectiveness depends on the context and the data structure.

### Hide

The hide strategy seeks to protect data from unnecessary visibility. Confidentiality technologies such as encryption, access control, secure channels and pseudonymization help ensure that only authorized parties can view or link data. The strategy also seeks to reduce linkability between datasets so that data from different sources cannot easily be combined to identify individuals.

Techniques such as mixed networks, privacy-preserving credentials and pseudonymous identifiers support this strategy. Hiding does not eliminate the need for good governance but reinforces technical protection.

### Separate

Separation reduces risk by avoiding unnecessary aggregation of data. Instead of storing all information in a central repository, data may be partitioned according to purpose, sensitivity or type. A single organization may legitimately hold financial data and health data about the same person, but combining these datasets into a single database would increase risk without increasing operational need.

Separation also extends to distributed processing. Local preprocessing on devices, distributed computation across multiple nodes and architectures that minimize centralization all reduce the attack surface and limit the consequences of breaches.

A prominent example is **federated learning**, a machine learning paradigm in which models are trained on decentralized data stored by individual clients or institutions. Only model updates are shared with a central aggregator, reducing the need to pool raw data.

### Aggregate

Aggregation aims to make individual-level data less exposed by summarizing them into groups or statistical results. Unlike hiding, aggregation transforms data so that detailed information is either removed or generalized. This might involve releasing counts instead of individual records, reducing geographic granularity, or applying anonymization techniques that enforce group-level indistinguishability.

Aggregation is especially important in open data and research contexts, where sharing insights is desirable but sharing raw data is too risky.

### Inform

The first of the process-oriented strategies, inform requires organizations to communicate clearly with data subjects about what data are collected, how they are used, what rights individuals have and how those rights may be exercised. This strategy seeks to address the longstanding challenge that privacy policies are often unreadable or overly vague. Although regulatory compliance demands transparency, meaningful transparency requires careful design, accessible language and user-centered communication strategies.

### Control

Control means giving data subjects meaningful choices about how their data are processed. This includes mechanisms for managing consent, selecting preferences, correcting errors or deleting data. Control mechanisms must not merely exist but must be easy to use and integrated into system workflows. The right to data portability, for example, requires not only legal provisions but also technical solutions that enable individuals to download or transfer their data.

### Enforce

Enforcement refers to internal organizational processes ensuring that privacy rules are actually followed. This includes implementing internal policies, training personnel, restricting access, maintaining secure configurations and ensuring that contracts with external processors align with privacy requirements. Enforcement bridges the gap between documented procedures and day-to-day operations.

### Demonstrate

Finally, the demonstrate strategy requires organizations to be accountable. They must document decisions, conduct audits, maintain logs, record consent, keep track of incidents and be prepared to demonstrate compliance to supervisory authorities. Demonstration is not only a defensive practice but also a proactive one, reinforcing trust with users, partners and regulators.

## Bringing It All Together

Privacy by design is more than a checklist; it is a mindset embedded in every stage of a system’s conception and operation. It requires understanding data flows, anticipating risks, balancing benefits and harms, and adopting both technical and organizational measures. The strategies described above offer guidance but must be adapted to each context, as no two systems are identical.

As data volumes grow and systems become increasingly interconnected, the importance of integrating privacy protections early and consistently becomes even more critical. Privacy by design ensures that systems remain respectful of individuals’ rights and resilient to evolving threats, laying the foundation for trustworthy data-driven innovation.

In the next chapters, we will explore concrete privacy-enhancing technologies, including anonymization methods, cryptographic tools and distributed learning techniques, that operationalize these strategies in practice.




