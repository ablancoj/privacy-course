# Privacy by design

## Risk assessment

- Describe any personal data processing in the system.
  - Collection, storage, analysis, exchange, etc.
- Identify likelihood of privacy threats.
  - Linking of personal data, re-identification, disclosure, etc.
  - May be in terms of probabilities.
- Identify impact of privacy threats.
  - May be in economic terms.
- Compute risk = Likelihood x Impact
- Propose countermeasures.

## Data strategies

### Minimize

- The amount of personal data that is processed should be restricted to the minimum possible (relates to minimization).
- By avoiding collection of unnecessary data, the possible privacy impact of a system is limited.
- Decide whether:
  - The processing of personal data is proportional to the purpose;
  - No other, less invasive means exist to achieve the same purpose.
- Design patterns: Select before you collect; anonymization, pseudonyms.


### Hide

- Any personal data and their interrelationships should be hidden from plain view (relates to information security).
- Doing so ensures personal data cannot be easily abused.
- The HIDE strategy seeks unlinkability and unobservability.
- Design patterns: encryption of data (stored or in transit), mix networks (to hide traffic patterns), attribute-based credentials for unlinkability, anonymization, pseudonyms.


### Separate

- Personal data should be processed in a distributed fashion, in separate compartments whenever possible.
- By separating the processing or storage of several sources of personal data that belong to the same person, complete profiles of that person cannot be made.
- Distributed rather than centralized processing.
- Data from separate sources stored in separate databases.
- Data to be processed and stored locally as much as possible.
- Database tables to be split when possible and rows in those table to be made difficult to link (by removing identifiers and using table-specific pseudonyms).
- For example, blockchain-based technologies, federated learning.


### Aggregate

- Personal data should be processed at the highest level of aggregation and with the least possible detail in which it is (still) useful.
- Aggregating information over groups of attributes or individuals reduces the detail of the information ⇒ data become less sensitive.
- If data are general enough that they can fit more than one person, they are not attributable to any single person ⇒ privacy is protected.
- Design patterns: k-anonymity, aggregation over time (e.g., in smart metering), location coarsening (in LBSs), differential privacy and other privacy models/anonymization techniques.


## Process strategies

### Inform

- Whenever data subjects use a system, they should be informed about which information is processed, for what purpose and by which means, and how is that information protected.
- Relates to transparency and openness.
- Clear documentation must be provided.
- In case information is shared with third parties, subjects should be informed about it.
- Subjects should also be informed about their data access rights and how to exercise them.
- Design patterns: Platform for Privacy Preferences (P3P), transparency-enhancing techniques.


### Control

- Data subjects should be given agency over the processing of their personal data (relates to individual rights).
- INFORM and CONTROL are intertwined:
  - Informing makes little sense if the subject has no control.
  - Control is impossible without the subject being informed.
- Access rights include the subject viewing, updating or even deleting her data.
- CONTROL interfaces should be easy to use.
- Design patterns: User-centric identity management, end-to-end encryption support control, intervenability techniques.


### Enforce

- A privacy policy compatible with legal requirements should be in place and should be enforced (for accountability).
- The policy ensures that the system respects privacy.
- The privacy level should meet all legal requirements.
- Technical protection mechanisms must exist that prevent policy violations.
- Governance structures to enforce the policy must be established.
- Design patterns: Access control, privacy rights management (a form of digital rights management involving licenses to personal data).


### Demonstrate

- The data controller must be able to demonstrate compliance with the privacy policy and applicable legal requirements (for accountability).
- This strategy goes beyond ENFORCE: not only must privacy be enforced but it must be done demonstrably.
- Design patterns: Privacy management systems, logging, auditing.
