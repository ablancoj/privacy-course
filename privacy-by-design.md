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



### Seattle example

### LINDDUN


## Data strategies

### Minimize

The amount of personal data processed should be restricted to the minimum necessary. By avoiding collection of unnecessary data, the system limits potential privacy impacts. Key questions include: Is the data processing proportional to the purpose? Are there less-invasive means to achieve the same goal? Typical design patterns supporting minimisation include “select before you collect,” anonymisation, or use of pseudonyms.

### Hide

Any personal data and their interrelationships should be hidden from plain view (reflecting the information security dimension). This strategy seeks unlinkability and unobservability: to ensure that personal data cannot be easily abused because they are concealed, encrypted or otherwise protected. Design patterns include encryption (data at rest or in transit), mixing networks to hide traffic patterns, attribute-based credentials, pseudonyms and anonymisation.

### Separate

Personal data should be processed in a distributed fashion, and data from separate sources should be stored or processed in distinct compartments where possible. The underlying rationale is that by separating storage or processing of data that belong to the same individual, you reduce the ability to build comprehensive profiles. Examples include storing different data types in separate databases, processing data locally rather than centrally, splitting database tables, and using federated learning or blockchain‐based approaches.


### Aggregate

Personal data should be processed at the highest level of aggregation and with the least detail necessary for the purpose. When data refer only to groups rather than to individuals, the sensitivity is reduced. Examples of supporting design patterns include k-anonymity, temporal aggregation (for example in smart metering), location coarsening in location-based services, and differential privacy.


## Process strategies

### Inform

Data subjects should be clearly informed about what information is being processed, for what purpose, by which means, and how it is protected. Transparency means providing clear documentation, notices, and informing subjects if data are shared with third parties. Also informing them about their access rights and how to exercise them. Design patterns include the Platform for Privacy Preferences (P3P), transparency enhancing tools.


### Control

Subjects should be given agency over the processing of their personal data, this ties to individual rights. Informing alone is insufficient unless the subject has some control, and control is impossible without being informed. Control includes enabling subjects to view, update, or delete their data; control interfaces should be easy to use. Design patterns include user-centric identity management, end-to-end encryption to give users control, intervenability.


### Enforce

A privacy policy compatible with legal requirements should be in place and must be enforced. This strategy ensures that the system respects privacy commitments. Technical protection mechanisms should exist to prevent policy violations, and governance structures must enforce the policy. Design patterns include access control, privacy rights management (a form of DRM for personal data).


### Demonstrate

The organisation (data controller) must be able to demonstrate compliance with the privacy policy and applicable legal requirements – this entails accountability. It goes beyond enforcement: not only must privacy be enforced, but the organisation must show demonstrably that it is being enforced. Design patterns include logging, auditing, privacy-management systems.
