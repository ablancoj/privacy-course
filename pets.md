# Privacy enhancing techniques


### Privacy-Enhancing Techniques (PETs)

Privacy-Enhancing Techniques are technological enablers of privacy by design. They allow organizations to provide core digital functions such as authentication, communication, and data analysis, while revealing minimal information about users. Most PETs are rooted in cryptography, which ensures confidentiality, integrity, and accountability without compromising anonymity.

Among these techniques, digital signatures guarantee authenticity but may expose identities. To address this, several privacy-preserving variants exist:

- Blind signatures enable a party to sign a message without reading it, allowing anonymous yet verifiable transactions (as in early e-cash and e-voting systems).

- Group signatures allow any member of a group to sign on behalf of all, ensuring anonymity within the group while enabling accountability through a trusted manager.

- Attribute-based signatures prove possession of a property (e.g., being over 18 or a licensed physician) without revealing identity.

- Zero-Knowledge Proofs (ZKPs) let someone prove that they know a secret or satisfy a condition without disclosing any details—key for authentication and blockchain privacy protocols.

Beyond authentication, PETs also support anonymous credentials and pseudonymization, enabling continuity of interaction without persistent identification. In communication systems, mix networks, onion routing, and the Tor network protect metadata, hiding who communicates with whom. More advanced approaches, like homomorphic encryption, secure multiparty computation (SMPC), and trusted execution environments (TEEs), allow computation on encrypted or distributed data without exposing its contents.

Some (often cryptographic) mechanisms can aid in the development of technologies which preserve the privacy of participants, sometimes to the level of anonymity.
These mechanisms (or the protocols built using them) are called privacy-enhancing techniques (PETs).
We next explore PETs to support identification and authentication, private communications, and private computations.

Privacy enhancing techniques (PETs) are technological mechanisms designed to help implement the principles of privacy by design—particularly those of minimization, hiding, separation, and control. Their goal is to enable organizations to develop services that respect users’ privacy and comply with data protection laws, not merely by policy but through the architecture of their systems. PETs include a wide range of cryptographic tools and communication protocols that allow systems to process, share, or verify information about individuals while revealing as little personal data as possible. They can enable users to interact with digital services in a way that maintains confidentiality and, in some cases, full anonymity—revealing only what is strictly necessary for the service to function.



## Identity and authentication

A first group of PETs deals with identification and authentication. These are essential for security—ensuring that only authorized users can access resources and that data or transactions come from legitimate sources—but they also play a crucial role in privacy. Traditional authentication mechanisms, like passwords or digital certificates, are based on proving one’s identity. However, many privacy-preserving techniques instead allow users to prove eligibility or authorization without revealing who they are. In this sense, they align with the GDPR’s principle of data minimization: authenticate the action, not the person.

A fundamental building block in this domain is the digital signature, a cryptographic mechanism that provides integrity (ensuring that a document has not been altered) and authenticity (verifying the source). It is based on asymmetric cryptography, where each participant has a pair of keys: a private key (kept secret) and a public key (shared openly). The signer uses their private key to sign a message, and anyone can verify the signature using the corresponding public key. To associate keys with real-world identities, digital signatures rely on a public key infrastructure (PKI), which certifies ownership of public keys. While standard digital signatures provide security, they do not inherently protect privacy—the signer is identified. However, several advanced variants extend this concept to allow anonymity or selective disclosure.

One of the earliest and most influential extensions is the blind signature, introduced by David Chaum in the 1980s. In a blind signature scheme, an authority can sign a message without seeing its contents. The message is mathematically “blinded” before being sent to the signer, who signs it without learning what they are signing. The user then “unblinds” the message to reveal a valid signature on the original content. This technique was the foundation of early digital cash systems, where a bank could validate electronic coins without knowing which specific coin belonged to which customer, thus allowing anonymous transactions. Blind signatures are also a cornerstone of many electronic voting protocols: a voter’s ballot is authenticated by the election authority (ensuring legitimacy) but remains secret, so no one can trace how an individual voted.

Another important PET in this context is the group signature. In this scheme, multiple users belong to a group that shares a common public key, while each individual has their own private signing key. When a message is signed by any group member, verifiers can confirm that it came from someone within the group—but not who exactly. This provides a balance between anonymity and accountability. Typically, a trusted group manager can revoke anonymity in exceptional cases (for example, if a user abuses their privileges), but outsiders cannot distinguish which member signed a message. Group signatures are useful in scenarios such as collective petitions, whistleblowing platforms, or any case where anonymity within a known group is required.

A related class of techniques includes identity-based and attribute-based signatures. Identity-based signatures simplify key management by allowing any text string—such as an email address or username—to act as a public key. This eliminates the need for a central certificate authority, as the identity itself serves to link the public key to the signer. In contrast, attribute-based signatures focus not on identity but on verifiable characteristics or attributes. A user can sign a message proving possession of certain properties—like being over 18, a licensed doctor, or a verified student—without revealing their actual identity. These systems issue keys associated with specific attributes, enabling “selective disclosure.” For instance, in a medical context, a nurse could digitally sign a prescription to prove their qualification without exposing their full professional or personal information.

The final and most general concept introduced in this lecture is the zero-knowledge proof (ZKP). A zero-knowledge proof allows one party (the prover) to convince another (the verifier) that they know a secret or that a statement is true, without revealing the secret itself. The classic example involves proving knowledge of a password or cryptographic key without ever transmitting it. This approach provides very strong privacy guarantees and forms the basis of many modern privacy-preserving systems, including cryptocurrencies and anonymous authentication protocols. ZKPs can be interactive or non-interactive and are used today in advanced frameworks such as zk-SNARKs (Zero-Knowledge Succinct Non-Interactive Arguments of Knowledge), which enable complex verifications—such as validating blockchain transactions—without revealing underlying data.

Altogether, these privacy enhancing techniques demonstrate that privacy and security can coexist when carefully designed. They allow systems to enforce trust, accountability, and correctness while minimizing the amount of personal information exposed at each interaction. In practice, PETs enable key privacy by design principles: minimize (by revealing the least information necessary), hide (through encryption and obfuscation), separate (by decoupling identities from transactions), and control (by giving individuals more say over what is revealed). These cryptographic and protocol-level mechanisms lay the foundation for modern privacy-preserving infrastructures, from secure digital payments and anonymous communication networks to federated identity management and privacy-aware authentication systems.

In addition to authentication and signing mechanisms, privacy enhancing techniques include a wider family of tools that support anonymous authorization and communication, ensuring that users can interact with digital systems or others without revealing their identity or personal information. These mechanisms enable anonymous credentials, pseudonymous identifiers, and private communication channels, extending privacy protection beyond single transactions to full data flows and online interactions.

Anonymous credentials are cryptographic constructs that allow individuals to prove they possess valid attributes or authorizations issued by a trusted authority—such as age, nationality, or membership—without revealing their identity or enabling linkage across different uses. They can be seen as a generalization of attribute-based signatures. A credential authority issues credentials containing various attributes, but when the holder uses them, they can selectively disclose only those necessary for a given service. For example, someone could prove they are over 18 or a resident of a particular region without revealing their name, date of birth, or exact address. Systems like IBM’s Idemix and Microsoft’s U-Prove were early practical implementations of anonymous credentials. These technologies embody the privacy by design principle of minimization and control, since they allow users to determine what information is revealed and to whom.

Another layer of protection arises from the use of pseudonyms. A pseudonym is an identifier that substitutes a real identity, enabling continuity of interaction—so that systems can, for example, recognize returning users—without revealing who those users truly are. Unlike complete anonymity, pseudonymity maintains linkability within a limited context but prevents cross-context correlation. For instance, a person might use one pseudonym for a medical platform and another for a discussion forum, with no means for external parties to link them. Pseudonym systems can be static, dynamic, or group-based, and are often managed by trusted intermediaries or cryptographic schemes that issue and rotate identifiers. The GDPR explicitly recognizes pseudonymization as a security measure that reduces privacy risk while preserving some data utility.



### Digital Signatures

In paper documents, handwritten signatures guarantee the authenticity of the document, and the signer cannot repudiate it. Moreover, the paper support gives some
protection against manipulation: deletions and additions can be detected, at least by
an expert. Digital signatures were created in order to guarantee the authenticity and
integrity in the case of electronic communications, and to avoid their repudiation.
Digital signatures were made possible by the deployment of public-key encryption.
In addition, digital signatures and the public key infrastructure can be used to provide authentication of individuals.

If both sender and receiver share some information, an alternative to digital signatures are message authentication codes (MACs). They are based on keyed cryptographic hash functions, and they can be used to guarantee the integrity of the
message. MACs are commonly used in the context of symmetric encryption communications, where sender and receiver share a secret key.

Next, we enumerate specific classes of digital signatures that enable authentication while being compatible with some user anonymity.

#### Blind Signatures

Blind signatures (Chaum 1983) are considered particularly useful for electronic
payment systems, electronic voting schemes and token-based access control mechanisms; a user may obtain a signature (e.g. a signed coin from a bank) such that the
signer does not know the contents of the message and cannot produce further valid
signatures.

#### Group Signatures

In a group signature scheme (Chaum and Van Heyst 1991), a set of users, called
members of the group, can issue signatures of arbitrary messages on behalf of the
group. A verifier can check the validity of the signature using the group public key.
The main interest in this kind of signature is that it ensures the privacy of signers
against potential verifiers, because a potential verifier cannot distinguish two signers from the same group.
A requirement of group signatures is the support for membership revocation of
misbehaving members without the need to update the group public key. To facilitate
member revocation, some members, called group managers, are endowed with the
capability to revoke membership.

#### Identity-based Signatures

Identity-based signature schemes, theorised in Shamir (1984) and with the first concrete protocol, based on the Weil pairing, shown in Boneh and Franklin (2001),
allow public keys to be arbitrary strings of some length, called identities. These
strings are associated with a user and reflect some aspect of her identity, e.g. her
email address. The corresponding secret key is then computed by a trusted entity
taking as input the user’s identity and, possibly, some other secret information, and
is sent to the user through some secure channel. Identity-based public key signature
schemes offer considerable flexibility in key generation and management.

#### Attribute-based signatures

Attribute-based signatures generalise identity-based signatures in that, instead of
having the users’ identities as credentials, they use properties, or attributes, of the
users as the latters’ credentials (in the attribute-based setting, the identity is one
more attribute of the user). Attribute-based signatures were introduced by Shanqing
and Yingpei (2008), inspired by previously existing attribute-based encryption
schemes, such as the one in Goyal et al. (2006). In attribute-based signatures (and
encryption) schemes, the users receive private key shares associated with their credentials, such as their name, age, country of residence, having or not a driving
licence, place of work, etc. Digital signatures are produced with respect to some
function of the users’ credentials, typically called a policy.
For example, a drugstore may accept drug prescriptions only if they are issued by
medical doctors or by nurses with a long working experience. In this scenario, prescriptions could be digitally signed under the policy role = “medical doctor” OR
(role = “nurse” AND experience = “10 years”). The identity of the signer in this
case is irrelevant.

### Zero-knowledge Proofs

Zero-knowledge proofs (Ben-Or et al. 1988b) allow a prover to convince a verifying
party of the truth of a statement without revealing any information other than the
truth of the statement. In particular, if the statement requires the prover to hold some
secret information, then the verifier does not learn this information—it is possible to
prove knowledge of a secret without revealing the secret itself. Statements that only
prove possession of a secret are known as zero-knowledge proofs of knowledge.
Proofs can be either interactive or non-interactive depending on whether the parties
can communicate during the proof. In general, non-interactive proofs (Blum et al.
1988) are considered more difficult since they cannot use interactive challengeresponse protocols and they require the random oracle model or a common reference string between parties. Whereas zero-knowledge proofs can be rather
inefficient, non-interactive proof systems built on bilinear groups (Groth and Sahai
2008) are particularly efficient for group-dependent problems where the secrets are
group elements or the exponents of a group element. As many useful cryptographic
schemes are built using bilinear pairings, particularly functional encryption, such a
proof system can be very useful for proving knowledge of a cryptographic secret
without revealing it.
Zero-knowledge proofs can be used to authenticate users holding cryptographic
devices, such as smartcards, without leaking any information about these users
except that they hold a valid card.

### Implicit Authentication

In implicit authentication, a server can authenticate users by checking whether
their behaviour is compatible or similar enough to their past-recorded behaviour.
In this context, the user’s behaviour can be modelled as a combination of features
such as her browsing history, usual location, keystroke patterns, usually visible
cell stations, etc.
In the study of Jakobsson et al. (2009), empirical evidence was given that the
features collected from the user’s device history are effective to distinguish users
and therefore can be used to implicitly authenticate them. The collection of these
data, however, may be too privacy-invasive. Proposals such as those by Safa et al.
(2014), Domingo-Ferrer et al. (2015) and Blanco-Justicia and Domingo-Ferrer
(2018) make use of homomorphic encryption and secure multiparty computation
to authenticate users from their past behaviour without forcing them to disclose
their profiles.

## Private communications

Anonymous communication networks protect not only the content of messages but also their metadata—who communicates with whom, when, and how often. Encryption alone secures message content, but it does not hide the fact that communication occurs between two parties. To protect this traffic information, several PETs have been developed. Early systems used mix networks, proposed again by David Chaum, where messages are collected, re-ordered, and re-encrypted by intermediary servers (“mixes”) before being forwarded, breaking the link between sender and recipient. Modern adaptations of this idea include onion routing, which encapsulates messages in multiple layers of encryption—like layers of an onion. Each intermediate node decrypts only one layer, learning only the next hop, not the original sender or final recipient.

The best-known implementation of onion routing is the Tor network (The Onion Router). In Tor, messages pass through a random path of volunteer-operated relays, each adding a layer of obfuscation. This makes it extremely difficult for any observer to correlate input and output traffic and identify who is communicating with whom. Tor provides strong anonymity guarantees for users browsing the web or using online services, though it introduces latency and can be vulnerable to correlation attacks if both endpoints are monitored. Still, it remains the most widely deployed practical system for anonymous communication, used by journalists, activists, and individuals seeking to avoid surveillance or profiling.



This section discusses the protection of communication channels. First, it describes
end-to-end encryption, which provides confidentiality of communications. It then
introduces anonymous channels. Having discussed mechanisms that allow users to
be authenticated without revealing their identities, it is logical to discuss communication channels that do not reveal their address, which is also part of their identity

### End-to-end Encryption

End-to-end encryption refers to the encryption of messages exchanged by two or
more parties without the intervention of a centralised server. The centralised server
may exist and support the transport of the messages but all this server sees is
encrypted content. This behaviour is the opposite of the traditional message
exchange protocols, in which the messages are only encrypted while in transit from
the parties to the central server or from the central server to the parties.
End-to-end encryption is typically supported by having all participants have a
key pair from a public-key encryption scheme. The centralised server, in addition to
supporting the exchange of messages, works as a public-key repository, where users
can find the public keys of the users to whom they want to send messages. Once a
user has obtained another user’s public key, she can use this public key to encrypt
the messages, which will only be decryptable by the owner of the corresponding
private key. A more efficient variant is for users to exchange random session keys
for symmetric encryption by enciphering them under their public-private pairs and
then encrypting the messages with a symmetric encryption scheme under these random temporal session keys.

### Anonymous Channels

Anonymous channels allow users to hide their address (e.g. the IP address) to the
service provider they are communicating with. Examples of anonymous channels
include mixnets and onion routing.
A mix network or mixnet is a routing protocol in which each of the network
nodes shuffles (and re-encrypts) all received messages before sending them to the
next node (Chaum 1981). The shuffling process is kept secret by each mix server.
Additionally, the sender of the message might successively encrypt the message
with each of the mix servers’ public keys. If that is the case, each mix server will
have to decrypt each of the encryption layers (as if peeling an onion) until the final
destination of the message. The ToR network (Dingledine et al. 2004) is an example
of this operation.

#### ToR


## Private computations

Beyond communication privacy, PETs also include techniques that allow data to be processed securely without exposing its contents. These privacy-preserving computation methods are essential when multiple parties want to perform joint analysis or computations on confidential data while maintaining confidentiality. One of the most powerful is homomorphic encryption, which allows computations—such as addition or multiplication—to be carried out directly on encrypted data. The result, once decrypted, matches the outcome that would have been obtained had the computation been performed on the plaintext. This makes it possible, for example, to analyze sensitive health or financial data stored in encrypted form without ever decrypting it. While fully homomorphic encryption is computationally intensive and still limited in scalability, partial or hybrid schemes are increasingly practical and used in cloud-based secure analytics.

A related concept is secure multiparty computation (SMPC), in which several parties jointly compute a function over their combined inputs while keeping each input private. No participant learns anything beyond the final result. This approach allows, for instance, hospitals or banks to collaborate on shared analyses—such as aggregated risk models or epidemiological statistics—without sharing raw data. Modern SMPC protocols, like Yao’s garbled circuits or secret-sharing-based systems, are mathematically rigorous and form the basis of privacy-preserving data collaboration frameworks.

Another important technological approach is the use of trusted execution environments (TEEs), sometimes called secure enclaves. These are hardware-based security features that create isolated areas within a processor where code and data can be executed securely, even if the surrounding system is compromised. TEEs can protect sensitive computations from being observed or tampered with, making them valuable for privacy-preserving cloud computing and edge devices.



Identity, authentication, and access control are central components of secure systems.
It is important that data assets be accessible only to authorized parties.
On the one hand, a sound authentication and authorization infrastructure prevents data breaches.
On the other hand, it allows responsibilities to be attributed in case of a breach, which contributes to a transparent data processing environment.
Several methods exist to verify the identity of individuals, that is, to authenticate them.
Some of them allow for the authentication of users without disclosing their identity.

This section describes mechanisms to perform computations on data while keeping
the data private. The GDPR accepts encryption as a valid protection mechanism if
the decryption keys are only available to those entitled to have them. However, most
data analyses are incompatible with most encryption procedures: users typically
require data in clear form to analyse them.
Nonetheless, the following encryption techniques do allow some computations
to be carried out directly on encrypted data, and are usually part of larger systems,
such as privacy-preserving data mining.

### (Partially) Homomorphic Encryption

Some encryption schemes are homomorphic in nature. Given two ciphertexts
encrypting two plaintexts, certain operations can be performed on the ciphertexts
such that the result can be decrypted to produce the outcome of applying an operation (not necessarily the same) on the plaintexts themselves. Thus, some computations can be performed on encrypted data. Schemes that exhibit homomorphic
properties for a specific operation are known as partially homomorphic encryption
schemes. Examples of this class are those in ElGamal (1985) and Paillier (1999).
On the other hand, if the set of permissible operations enable arbitrary computations
to be performed, then the schemes are referred to as fully homomorphic (Gentry
2009; Gentry et al. 2013). Although fully homomorphic schemes are in principle
very powerful, currently available instances also involve very substantial overhead
and storage expansion. For that reason, less powerful schemes, known as somewhat
homomorphic, are sometimes preferred: under these schemes, the number of operations that can be performed on ciphertext before decryption will no longer succeed
is limited.


### Multi-party Computation

Secure multiparty computation protocols allow a set of parties to compute a joint
function of their inputs in a secure way without requiring a trusted third party.
During the execution of the protocol the parties do not learn anything about each
other’s input except what is implied by the output itself.
A general solution for the secure computation of functions among two players
was introduced in Yao (1986). The main idea of these protocols was to describe the
function as a circuit, and to compute every gate of the circuit in a secure way. This
idea was extended to the multi-partite setting in Goldreich et  al. (1987). They
showed how to create a secure multiparty computation protocol that allows playing any game and does not leak any information if the majority of the participants are
honest. These protocols are computationally secure. The first unconditionally secure
multi-party computation protocols were presented in Ben-Or et  al. (1988a) and
Chaum et al. (1988). These authors gave protocols to compute any arithmetic function in a secure way when at least two thirds of the parties are honest.
Two of the main open problems in secure multiparty computation are: (i) to relax
the assumptions on the behaviour of the players, and (ii) to reduce the computational and communication costs of the protocols for interesting families of functions. It should be observed that, in the general solutions described above, the
computational costs of the protocol depend on the size of the circuit defining the
function.
The most important properties of secure multiparty computation protocols are
privacy and correctness. Another important property is fairness. A protocol is fair if
there are no differences between the players when it comes to obtaining the output.
That is, a protocol is fair if either everybody receives their output, or no one does.

# Privacy-Enhancing Techniques

## Introduction

In the previous chapters we explored the regulatory foundations of privacy, the logic of risk assessment, and the system-level mindset captured by privacy by design. We now move from principles to practice. This chapter introduces **privacy-enhancing techniques**—often abbreviated as PETs—concrete technological mechanisms that support privacy goals across identification, communication, and computation. These are the tools that make privacy by design operational, enabling systems to minimize data collection, hide sensitive information, separate data flows, and aggregate results without exposing individuals.

Privacy-enhancing techniques range from cryptographic primitives to communication protocols and secure computation methods. Some aim to strengthen authentication while reducing disclosure. Others protect the confidentiality and unlinkability of messages. Others enable computations on data without revealing the underlying information. Together, they form a growing toolbox for privacy engineers, security practitioners, and data-intensive services that must comply with data protection requirements while still delivering useful functionality.

This chapter focuses on three families of PETs: **techniques for identification and authentication (with or without anonymity), techniques for secure and private communication, and techniques for privacy-preserving computation**. Database protection and statistical disclosure control will be covered in later chapters.

## Identification, Authentication, and Anonymity

The first family of privacy-enhancing techniques concerns the problem of identifying and authenticating individuals while controlling how much personal information such processes reveal. Authentication is central to security: it ensures that only authorized people access protected resources and helps attribute responsibility in case of misuse or breach. At the same time, unnecessary identity disclosure is itself a privacy risk. PETs in this category attempt to reconcile these two aims—strong authentication with minimal identity leakage.

### Digital Signatures: A Foundation

Most of the techniques in this category build upon **digital signatures**, a standard tool in public key cryptography. A digital signature enables a signer to attach a piece of cryptographic information to a message, proving two things: that the signer is indeed the author and that the message has not been altered. Verification is done with a public key, while signing uses a private key known only to the signer. A public key infrastructure (PKI) links these keys to real-world identities through trusted certificate authorities.

Digital signatures underlie many everyday technologies—from secure web browsing (HTTPS) to electronic administrative services. In their basic form, however, they always tie a signature to an identifiable individual or entity. A range of extensions modify this model to offer stronger privacy.

### Blind Signatures

A **blind signature** allows an authority to sign a message without learning its content. Before sending a message for signing, the requester blinds it using a cryptographic transformation. The signer applies their signature to the blinded message and returns it. The requester then unblinds the result to obtain a valid signature on the original message.

This mechanism is essential when an authority needs to validate the format or legitimacy of something—such as a voting ballot or a digital payment token—without learning the sensitive underlying information. Blind signatures were first proposed for electronic cash systems, where banks could sign digital “coins” without tracking how they were spent. They remain a foundational tool in electronic voting protocols, ensuring that authorities can verify ballots without learning how individuals voted.

### Group Signatures

A **group signature** scheme allows any member of a defined group to sign messages on behalf of the group in a way that ensures verifiability but preserves anonymity. A single public key corresponds to the entire group; each member holds a different private key. When a verifier checks a group signature, they can confirm that someone in the group signed the message, but they cannot identify which member it was.

Group signatures are useful in scenarios where individual identity is irrelevant, unnecessary, or risky to expose. They can support anonymous access to resources, collaborative requests, or group-based credentials. Importantly, group managers can add or revoke members, making the scheme adaptable to real-world organizational structures.

### Identity-Based and Attribute-Based Signatures

In an **identity-based signature** scheme, public keys are arbitrary strings—such as an email address—rather than long random numbers. This eliminates the need for a traditional PKI, since the “identity” embedded in the public key already conveys the needed linking information. While such schemes tie keys to identities more directly, the fact that public keys can be *any* arbitrary string opens the door to more privacy-preserving variants.

Among these variants, **attribute-based signatures** are particularly powerful. Instead of revealing a full identity, signers reveal only specific, certified attributes—such as “is a physician,” “is over 18,” or “is an employee of a given department.” The signature attests that these attributes are valid without exposing who the signer is. This makes it possible to enforce eligibility or authorization rules while minimizing unnecessary identity disclosure.

### Zero-Knowledge Proofs

Zero-knowledge proofs represent a different paradigm. Instead of proving who you are, a zero-knowledge proof allows you to prove that you know some secret or satisfy some property *without revealing the secret itself*. Classic examples include demonstrating knowledge of a password without revealing it, or proving that a ballot is well-formed without revealing the vote.

Zero-knowledge proofs are interactive protocols in which a prover convinces a verifier through repeated challenges. Modern constructions allow non-interactive proofs, making them widely applicable in systems such as electronic voting, privacy-preserving identity systems, and blockchain-based smart contracts.

Together, these mechanisms illustrate that authentication does not always require identification. Systems can verify eligibility, correctness, or legitimacy while preserving user anonymity—a core privacy by design objective.

## Secure and Private Communications

The second family of PETs concerns how data move through networks. Even when messages are encrypted, metadata such as who is communicating with whom, when, and how frequently can reveal sensitive information. PETs in this category aim to protect both message content and communication patterns.

### End-to-End Encryption

Traditional communication architectures often encrypted messages between each user and an intermediary server but required the server itself to read the plaintext in order to forward messages. End-to-end encryption (E2EE) eliminates this vulnerability by ensuring that only the communicating endpoints can decrypt the message content. The server acts merely as a router or temporary storage node.

E2EE relies on public key encryption. When sending a message, the sender uses the recipient’s public key to encrypt a randomly generated symmetric key (the “digital envelope”), which then protects the actual message. The server cannot decrypt any part of the transmission, reducing the threat of unauthorized access, surveillance, or internal misuse.

Modern messaging systems such as Signal and WhatsApp use variants of this protocol, making E2EE a widely deployed privacy-enhancing technology.

### Protecting Metadata: Anonymous Channels

End-to-end encryption secures content but not metadata. Intermediaries can still observe who is talking to whom. To address this, anonymous communication channels hide user IP addresses and obscure message routing.

The simplest approach is the **virtual private network (VPN)**, which channels all traffic through a proxy server. While this hides the client’s IP from destination servers, it shifts trust to the VPN provider, who now sees all traffic patterns. To reduce this concentration of trust, onion routing systems distribute trust across multiple intermediate nodes.

The **Tor network** implements onion routing: the sender wraps the message in multiple layers of encryption, each layer corresponding to an intermediate node. Each node peels off one layer, learning only the next hop and nothing about the original sender or final destination. This prevents any single intermediary from reconstructing the communication path.

A related approach is the **mix network**, which aggregates and shuffles messages before forwarding them. Mix networks break the timing correlations that might otherwise reveal communication links, making them valuable in applications such as electronic voting.

These anonymous channels illustrate a general lesson: protecting privacy in communication requires more than encryption. It requires hiding the *structure* of communication itself.

## Privacy-Preserving Computation

The third family of PETs enables data processing without revealing the underlying data. This is essential in scenarios where sensitive data must be analyzed by untrusted servers, shared across organizational boundaries, or combined to compute aggregate information without exposing individual contributions.

### Homomorphic Encryption

Homomorphic encryption schemes allow mathematical operations to be performed directly on encrypted data. After computation, the result—still encrypted—can be sent back to the data owner, who decrypts it to obtain the output as if the operations had been performed on the plaintext.

Some schemes support only one type of operation, such as addition or multiplication. These are called **partially homomorphic** schemes; classic examples include RSA (multiplication) or Paillier (addition). More recently, **fully homomorphic encryption** (FHE) schemes have been developed that support both. FHE is computationally heavy but rapidly improving, and its resistance to quantum attacks makes it attractive for long-term deployments.

Homomorphic encryption is suitable for numerical data and provides strong confidentiality even when outsourcing computation to untrusted environments.

### Secure Multi-Party Computation

Secure multi-party computation (MPC) allows several parties to jointly compute a function on their combined inputs without revealing those inputs to one another. Each party learns only the final output and nothing more.

MPC protocols can compute tasks such as averages, sums, or complex Boolean functions. They rely on advanced cryptographic tools such as garbled circuits and often build upon secret sharing mechanisms. Although historically too inefficient for widespread use, MPC has seen rapid improvement, with practical deployments in areas such as health data collaboration, pandemic analytics, and joint fraud detection.

The key idea is collaboration without disclosure: multiple entities can benefit from shared insights while retaining local control over sensitive data.

### Secret Sharing

Secret sharing schemes split a secret into multiple “shares,” distributing them among participants. Only certain authorized subsets—defined by an *access structure*—can reconstruct the secret. Unauthorized subsets learn nothing.

The most common pattern is threshold sharing: from *n* shares, any *k* can reconstruct the secret, while fewer provide no information. Secret sharing serves as a foundational building block for MPC, threshold signatures, and distributed key management. Its power lies in decentralization: no single compromised party can leak the underlying secret.

## Bringing PETs Into Privacy by Design

Privacy-enhancing techniques give concrete form to the strategies introduced in earlier chapters. They help minimize data collection by reducing the amount of identity information needed for authentication. They enforce hiding through strong cryptography and anonymous routing. They enable separation by distributing trust across multiple nodes or entities. They support aggregation by allowing computations on encrypted or decentralized data.

Importantly, PETs are not standalone solutions. Their effectiveness depends on proper integration into system architecture, careful risk assessment, and ongoing governance. They are also not universal: each technique has strengths, weaknesses, computational considerations, and appropriate use cases.

As systems begin to rely more heavily on data to deliver personalized services, analytics, and machine learning, the ability to process data without unnecessary exposure becomes increasingly critical. PETs offer a pathway forward—allowing organizations to uphold privacy protections while still extracting value from data.

The next chapters will turn to **database protection and anonymization**, where statistical approaches complement the cryptographic techniques introduced here. There, we will explore attacks based on re-identification and attribute inference and study methods for making datasets safe to publish or share.

