# Introduction and GDPR

When we talk about security, we refer to a set of mechanisms designed to protect data and systems against unauthorized access or damage. In information security the classic reference is the CIA triad, which does not allude to the U.S. intelligence agency but to three fundamental properties: confidentiality, integrity, and availability. Confidentiality means that only authorized people or entities can read or access specific resources; it is achieved through access control, authentication, and encryption. Integrity concerns the ability to modify data: only those who are authorized should be able to alter information, and any unauthorized or accidental change, such as noise introduced into a dataset, violates integrity. Availability refers to ensuring that all authorized users can access resources whenever they need them, even after disasters or technical failures. Security, therefore, is largely technical and aims at the protection of systems as a whole.

Privacy, in contrast, is the control that individuals have over their own personal data. It is closely related to confidentiality but focuses on the rights of data subjects rather than on the resilience of systems. Privacy centers on people: the information that identifies them and the power relationships surrounding its collection and use.

## Ethical principles

From an ethical perspective, several principles justify the right to privacy. The first is the principle of “do no harm.” Our professional and everyday actions should avoid causing harm to others, even when they bring potential benefits. Collecting or leaking personal data can harm individuals in multiple ways. One obvious dimension is **safety**: sharing too much information, such as posting travel plans or location data on social media, can expose people to physical risks like burglary or stalking. Another dimension is **fairness** and non-discrimination: the misuse of personal data can lead to biased treatment or exclusion based on gender, age, religion, or other sensitive categories. Finally, there is **autonomy**. Constant surveillance by corporations or governments limits the range of actions individuals feel free to take. Being permanently observed reduces one’s ability to act or express oneself freely. Protecting privacy, therefore, also protects personal autonomy.

## Legal principles

Legally, privacy has a long history. The first explicit reference appeared in 1890 in the famous article by Samuel Warren and Louis Brandeis, who defined privacy as “the right to be left alone.” Their concern emerged in response to new photographic technologies and intrusive journalism, the paparazzi of their day. Later, privacy was recognized as a human right in the Universal Declaration of Human Rights (1948): “No one shall be subjected to arbitrary interference with his privacy, family, home or correspondence.” The term “correspondence,” initially referring to letters, has since expanded to encompass digital communications. Within the European context, the Charter of Fundamental Rights of the European Union reaffirmed this right, explicitly including digital communications and the protection of personal data: data must be processed fairly, with consent, and under clear rules.


:::{admonition} Warren II y Brandeis, 1890 
Right to be left alone.
:::

:::{admonition} Article 12, Universal Declaration of Human Rights
No one shall be subjected to arbitrary interference with his privacy, family, home or correspondence, nor to attacks upon his honour and reputation. Everyone has the right to the protection of the law against such interference or attacks.
:::

:::{admonition} Article 7, Charter of Fundamental Rights of the European Union, 2000
Everyone has the right to respect for his or her private and family life, home and communications.
:::

:::{admonition} Article 8, Charter of Fundamental  Rights of the European Union, 2000
1. Everyone has the right to the protection of personal data concerning him or her.
2. Such data must be processed fairly for specified purposes and on the basis of the consent of the person concerned or some other legitimate basis laid down by law. Everyone has the right of access to data which has been collected concerning him or her, and the right to have it rectified.
3. Compliance with these rules shall be subject to control by an independent authority.
:::
        
## Personal data

Personal data are any data that refer to an identifiable individual. We can distinguish three main categories. Direct identifiers uniquely identify a person—examples include name, national identification number, social security number, or phone number. Indirect identifiers do not identify someone by themselves but can do so when combined with other pieces of information: age, gender, postal code, or IP address. Sensitive information comprises attributes that should not be publicly linked to an individual, such as medical diagnoses, religious beliefs, or sexual orientation. Protecting privacy involves preventing both direct and indirect identifiers from being combined in ways that re-identify people. Even when direct identifiers are removed, datasets may still enable re-identification. Combining indirect clues often suffices to identify individuals.


::::{grid} 1 1 2 3

:::{card} Direct identifiers 
:header: a
Attributes that uniquely identify a data subject, such as their name or social security number.
:::

:::{card} Inderict identifiers
Attributes that, when combined, can uniquely identify a daata subject, such as age, gender, and address.
:::

:::{card} Sensitive information
Attributes that reveal especially protected information about the data subject, such as a medical diagnosis, sexual orientation, or religious beliefs.
:::
::::

:::{admonition} Example
:class: note
<span style="background-color:black">Barack Hussein Obama II</span> (born in <span style="background-color:black">Hawaii</span> on <span style="background-color:black">August 4th 1961</span>) is an <span style="background-color:black">american</span> lawyer and politician who served as the <span style="background-color:black">44nd</span> President <span style="background-color:black">of the United States</span>, from January 20th <span style="background-color:black">2009</span> until January 20th <span style="background-color:black">2017</span>. He is a member of the <span style="background-color:black">Democratic</span> Party, and was <span style="background-color:black">the first African American to serve as</span> President. Previously, he had been a Senator for the State of <span style="background-color:black">Illinois</span>.
:::

:::{admonition} Example
:class: note toggle
<span style="background-color:black">Barack Hussein Obama II</span> (born in <span style="background-color:black">Hawaii</span> on <span style="background-color:black">August 4th 1961</span>) is an american lawyer and politician who served as the <span style="background-color:black">44nd</span> President of the United States, from January 20th <span style="background-color:black">2009</span> until January 20th <span style="background-color:black">2017</span>. He is a member of the Democratic Party, and was <span style="background-color:black">the first African American to serve as</span> President. Previously, he had been a Senator for the State of Illinois.
:::

:::{admonition} Example
:class: note toggle
<span style="background-color:black">Barack Hussein Obama II</span> (born in Hawaii on August 4th 1961) is an american lawyer and politician who served as the 44nd President of the United States, from January 20th 2009 until January 20th 2017. He is a member of the Democratic Party, and was the first African American to serve as President. Previously, he had been a Senator for the State of Illinois.
:::

:::{admonition} Example
:class: note toggle
Barack Hussein Obama II (born in Hawaii on August 4th 1961) is an american lawyer and politician who served as the 44nd President of the United States, from January 20th 2009 until January 20th 2017. He is a member of the Democratic Party, and was the first African American to serve as President. Previously, he had been a Senator for the State of Illinois.
:::

| Direct identifiers | Indirect identifiers | Confidential information     |
|--------------------|----------------------|------------------------------|
| Name               | Age                  | Transactions (e.g. purchases)| 
| Email address      | Gender               | Salary                       |
| Mobile phone number| Race                 | Credit ranking               |
| National ID number | Date of birth        | Insurance policy             |
| Passport number    | Address              | Medical status               |
| Account number     | Postal code          | Vaccination status           |
| SSN number         | Job title            | Sexual orientation           |
| Social media name  | Company name         | Religious beliefs            |
|                    | Marital status       |                              |
|                    | Height               |                              |
|                    | Weight               |                              |
|                    | IP address           |                              |
|                    | GPS location         |                              |


## Threats to privacy

The threats to privacy are numerous and pervasive. Some stem from state surveillance: governments deploy cameras, digital identity systems, and intelligence programs that monitor communications, such as the NSA’s PRISM program revealed by Edward Snowden. Others arise from corporate practices, as in the Cambridge Analytica scandal, where data collected through Facebook were used to profile and influence voters. Online tracking is another widespread threat. Most websites embed third-party cookies or pixels that follow users across pages, building detailed behavioral profiles. Recommendation systems on platforms like Amazon, YouTube, or TikTok rely on similar profiling to predict preferences and maximize engagement. Beyond browsing, smart devices—phones, wearables, Internet-of-Things appliances—continuously collect and transmit data about our habits. Sometimes the scale is astonishing: connected washing machines sending gigabytes of data daily, or robotic vacuum cleaners uploading photos of private spaces. Even apparently innocent games on social media (“What’s your elf name?”) harvest birth dates and initials. Data brokers aggregate publicly available or purchased data from multiple sources and resell it to advertisers or other organizations, operating in a legal gray area, especially outside Europe. Finally, data breaches occur when systems are hacked or mismanaged, exposing large volumes of personal information. Users can check whether their credentials have appeared in known leaks using services such as Have I Been Pwned.

	
## General Data Protection Regulation

These persistent risks motivated modern privacy regulation, notably the General Data Protection Regulation (GDPR) adopted by the European Union in 2016. Although European, the GDPR has effectively become a global benchmark because it applies to any organization that processes the personal data of EU citizens, regardless of where it operates. Similar frameworks in Canada, Australia, and California mirror its provisions. Within the EU, the regulation harmonizes data-protection standards so that personal data can move freely across member states, and transfers to non-EU countries are allowed only when comparable safeguards exist.

### Definitions

The GDPR defines key roles in the data-processing ecosystem. The **data subject** is the individual to whom the data relate. The **controller** determines the purposes and means of processing and bears primary responsibility. The **processor** acts on behalf of the controller—for example, a hospital using a cloud provider such as Microsoft Azure to store records remains the controller, while Azure is the processor. Both are bound by the regulation. **“Processing”** itself is defined very broadly: any operation performed on personal data: collection, storage, analysis, transmission, even deletion, counts as processing.

Consent under the GDPR must be freely given, specific, informed, and unambiguous. Services cannot assume consent, they must explain clearly what data they collect and why. In practice this requirement generated the now-familiar cookie banners on websites. Pseudonymization is a protective measure that replaces direct identifiers with pseudonyms or hashed values, making re-identification harder but still possible, since the mapping can be reversed. Anonymization goes further by eliminating both direct and indirect identifiers irreversibly, preventing any link to individual persons. The regulation pays special attention to genetic, biometric, and health data, as these reveal highly personal information not only about individuals but also about relatives. The use of biometric identification by artificial-intelligence systems, for example, is largely prohibited in the EU except for limited law-enforcement purposes.


- **Personal data** is any information relating to an identified or identifiable natural person (‘data subject’).
- An identifiable **data subject** is one who can be identified, directly or indirectly:
	- To an **identifier** such as a name, an identification number, location data, an online identifier, etc.
	- To one or more **factors** specific to the physical, physiological, genetic, mental, economic, cultural, or social identity **of that natural person** (confidential attributes).
- A **data subject** is a natural person.
- A **controller** is an entity that determines the purposes and means of the processing of personal data.
- A **processor** is an entity that processes personal data on behalf of the controller.
- **Processing** is any operation or set of operations that are performed on personal data or on sets of personal data, whether or not by automated means.
	- collection, recording, organization, structuring, storage, adaptation or alteration, retrieval, consultation, use, disclosure by transmission, dissemination or otherwise making available, alignment or combination, restriction, erasure or destruction.
- **Consent** of the data subject means any freely given, specific, informed, and unambiguous indication of the data subject’s agreement to the processing of personal data relating to him or her.
- **Genetic** data relate to the inherited or acquired genetic characteristics of a person which give unique information about their physiology or their health and which result from an analysis of their biological sample.
- **Biometric data** result from specific technical processing relating to the physical, physiological, or behavioral characteristics of a person, which allow or confirm their unique identification.
- **Data concerning health** relate to the physical or mental health of a person, including the provision of health care services, which reveal information about their health status.
- **Pseudonymisation** means the processing of personal data in such a manner that the personal data can no longer be attributed to a specific data subject without the use of additional information, provided that such additional information is kept separately and is subject to technical and organizational measures to ensure that the personal data are not attributed to an identified or identifiable natural person.
- **Data anonymization** is the process of transforming or removing personally identifiable information (PII) from data sets, so that the individuals who contributed the data cannot be identified.

### Principles of the regulation

The GDPR establishes a series of principles that organizations must follow: lawfulness, fairness, and transparency in processing; purpose limitation, meaning data collected for one purpose cannot be reused for another without new consent; data minimization, requiring the least amount of data necessary; accuracy, ensuring information is correct and up-to-date; storage limitation, preventing indefinite retention; integrity and confidentiality, which demand appropriate technical and organizational security; and accountability, obliging controllers to demonstrate compliance. Lawfulness usually rests on valid consent, though the concept of what constitutes a “justified reason” remains broad. Consent must be demonstrable and revocable at any time, and minors under sixteen cannot legally consent to processing.

- Any processing of personal data must be performed under the principles of **lawfulness**, **fairness**, **transparency**, **purpose limitation**, **data minimization**, **accuracy**, **storage limitation**, **integrity**, **confidentiality**, and **accountability**.
- It is considered lawful if it is consented, necessary to fulfill a contract, obliged by law, necessary to protect vital interests of the subject or another person, for the public interest, or in the legitimate interest of the controller.
	- The controller must be able to clearly **demonstrate the consent** of the data subject.
	- Consent can be withdrawn at any time.
	- Children under 16 cannot consent.
- Processing of personal data revealing 
	- racial or ethnic origin, 
	- political opinions, 
	- religious or philosophical beliefs, 
	- or trade union membership,
- and the processing of 
	- genetic data, 
	- biometric data for the purpose of uniquely identifying a natural person,
	- data concerning health, 
	- or data concerning a natural person’s sex life or sexual orientation 
- shall be prohibited.
- Exceptions:
	- explicit consent or manifestly made public by the data subject;
	- provision and management of employment, social security, and healthcare services;
	- public interest in the area of public health, such as protecting against pandemics or ensuring high quality and safety of health care and medicinal products or devices;
	- archiving purposes in the public interest, research purposes.
	- protect vital interests and cannot consent;
	- legitimate activities of a foundation, or not-for-profit body;
	- courts acting in their capacity;
	- substantial public interest;

### Rights of the data subject

Data subjects enjoy several rights: access to their data, rectification of errors, erasure (the “right to be forgotten”), restriction of processing, and portability so that their data can be transferred to another service. Companies must provide clear privacy policies explaining the purpose of processing, the identity of controllers and processors, retention periods, and procedures for exercising rights. In practice, some organizations implement these mechanisms better than others—Google’s data-management tools are often cited as relatively accessible examples.

- Articles 12 to 14 refer to privacy policies and what information the controller has to give the data subject, including the identity of the controller, the purpose for the data collection, and the rights of the subject.
- The rest of the chapter describes several rights of the subjects, such as:
	- Right of access, rectification, and erasure (‘right to be forgotten’).
	- Right to restriction of processing.
	- Right to data portability.

### Controller and processors

Controllers and processors have extensive obligations. They must guarantee the rights of data subjects, conduct privacy risk assessments and data protection impact assessments, apply privacy-by-design and privacy-by-default principles in technical and organizational decisions, keep detailed records of processing activities, and appoint a Data Protection Officer (DPO) when required by scale or sensitivity. They must also cooperate with supervisory authorities and notify both authorities and affected individuals in the event of data breaches. The degree of cooperation often influences the magnitude of penalties.

- Ensure the rights of data subjects.
- Conduct continuous privacy risk and data protection impact assessments.
- Apply privacy-by-design and privacy-by-default principles and use appropriate technical and organizational measures.
- Record processing activities.
- Appoint a Data Protection Officer.
- Communicate and collaborate with authorities (and data subjects) in cases of data breaches.

#### Data Protection Officer
- Inform and advice controllers and processors of their obligations.
- Monitor compliance.
- Advice on data protection impact assessment.
- Act as a contact point and cooperate with the supervisory authority.

### Other chapters

Each EU country has its own supervisory authority, such as Spain’s Agencia Española de Protección de Datos, which coordinates with counterparts across Europe. The regulation also foresees certification mechanisms to signal compliance, though these have proven difficult to implement because privacy challenges vary widely by context. Non-compliance can lead to substantial fines: up to four percent of a company’s global annual turnover.

- Description of supervisory authorities.
- Codes of conduct and privacy certifications.
- Transfers of data to third countries.
- Remedies, liability, and penalties.
