# Introduction and GDPR


## Ethical principles





- Security
- Fairness and non-discrimination
- Autonomy


## Legal principles


## Personal data

```{note}
Barack Hussein Obama II (born en Hawaii on August 4th 1961) es an american lawyer and politician who served as the 44nd President of the United States, from January 20th 2009 until January 20th 2017. He is a member of the Democratic Party, and was the first african-american to serve as President. Previously, he had been a Senator for the State of Illinois.
```

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

## Relevant cases

### Prism

PRISM es un programa secreto de la NSA que fue revelado por Snowden. A través de PRISM, la NSA obtenía acceso a los servidores de compañías tecnológicas estadounidenses, como Google, Facebook, Apple, Microsoft, Yahoo!, entre otras.
PRISM estaba diseñado para monitorear las actividades de personas consideradas "amenazas" o "sospechosas", pero la magnitud de la recolección de datos era mucho mayor, ya que afectaba a millones de personas alrededor del mundo.
El programa UPSTREAM permitía a la NSA recopilar información de los routers en buena parte del mundo.
Xkeyscore era una interfaz que permitía el acceso a los datos privados recolectados a partir de algún identificador.

![alt text](figs/snowden.png)
![alt text](figs/prism.png)

### Cambridge analytica

![alt text](figs/cambridge-analytica.png)

Cambridge Analytica obtuvo datos de 87 millones de usuarios de Facebook sin su consentimiento.
Los datos fueron usados para crear perfiles psicológicos y influir en elecciones, como las de EE. UU. en 2016.
El caso reveló cómo los datos personales pueden ser explotados para manipular la opinión pública.
Facebook fue multado con 5 mil millones de dólares y el caso impulsó la creación de regulaciones de privacidad, como el RGPD.


## Threats to privacy

Vigilancia masiva
Perfilado y recomendaciones
Seguimiento en línea (tracking)
Dispositivos inteligentes (smartphones e IoT)
Recolección excesiva de datos
Redes sociales y sobreexposición
Compartición, venta y publicación de datos
Brechas de datos


### Mass surveillance

### Profiling and recommendations

La información personal recogida puede ser utilizada para crear perfiles de usuario.
Identificadores, actividad en la red, fotografías, localización, contactos, likes, clicks, mensajes, pagos…
Uniendo, enlazando y analizando estos datos se nos pueden sugerir productos, nuevos contactos, viajes, películas, etc.
Las cookies y el browser fingerprinting son herramientas comunes para este fin.


### Browsing patterns

#### Cookies
#### Browser fingerprinting

### Smartphone Apps

### Smart devices (IoT)

### Excessive data requests

### Social media overexposure

![alt text](figs/elf-name.png)

### Sharing, sale, and publishing

Es habitual que empresas compartan datos privados de sus clientes. Estas comparticiones se suelen hacer al amparo de acuerdos de confidencialidad.
Otros datos, especialmente de agencias estadísticas, pueden ser compartidos a terceros con fines de investigación.
Los data brokers se dedican a recolectar y vender datos personales.
Una protección incorrecta podría llevar a la revelación de datos personales.


### Data breaches




## Basic privacy principles
- Privacy is a fundamental human right:
	- Article 12, Universal Declaration of Human Rights
	- Articles 7 and 8, Charter of Fundamental Rights of the EU
- However, in the digital world
	- Data collectors determine what and how data are collected and processed.
	- Data subjects whose privacy is at stake need privacy protection.
- It is an ethical principle to do no harm.
	- Leakage of personal data may lead to, on the one hand, attempt against the fundamental rights of people and, on the other hand, lead to further damage:
		- Leakages of personal data are a great tool for (cyber-)criminals.
		- Some private information may lead to discrimination.
		- Lack of privacy may lead to lack of autonomy.
- Thus, technologies must not only be designed to collect and process more data more efficiently but also to protect privacy.
	- People must not be put under risk just for the sake of discovery.
- Privacy-enhancing techniques (PETs) seek to minimize the processing of personal data.
- Yet, privacy cannot be guaranteed only with technology. 
	- A legal framework is needed.
	
## General Data Protection Regulation
- The General Data Protection Regulation (GDPR) lays down rules relating to the protection of natural persons w.r.t. the processing of personal data.
- GDPR protects fundamental rights and freedoms of natural persons and in particular their right to the protection of personal data.
- Since the GDPR harmonizes the regulation in all member states, personal data can be freely transferred between EU countries.
	- Additionally, all entities collecting data from European citizens must adhere to the regulation, making the GDPR a sort of worldwide standard for privacy protection.

### Definitions
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
- Articles 12 to 14 refer to privacy policies and what information the controller has to give the data subject, including the identity of the controller, the purpose for the data collection, and the rights of the subject.
- The rest of the chapter describes several rights of the subjects, such as:
	- Right of access, rectification, and erasure (‘right to be forgotten’).
	- Right to restriction of processing.
	- Right to data portability.

### Controller and processors
- Ensure the rights of data subjects.
- Conduct continuous privacy risk and data protection impact assessments.
- Apply privacy-by-design and privacy-by-default principles and use appropriate technical and organizational measures.
- Record processing activities.
- Appoint a Data Protection Officer.
- Communicate and collaborate with authorities (and data subjects) in cases of data breaches.

### Data Protection Officer
- Inform and advice controllers and processors of their obligations.
- Monitor compliance.
- Advice on data protection impact assessment.
- Act as a contact point and cooperate with the supervisory authority.

### Other chapters
- Description of supervisory authorities.
- Codes of conduct and privacy certifications.
- Transfers of data to third countries.
- Remedies, liability, and penalties.
