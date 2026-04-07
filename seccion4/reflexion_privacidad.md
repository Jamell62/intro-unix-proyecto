#Research Questions
1. What is asymmetric encryption (public/private key) and how does it work in the context of GPG? What is the difference between encrypting a message and digitally signing it? 

Asymmetric encryption is a method where “users do not share a common secret key (private key); instead, each user creates their own key pair, consisting of a secret or private key and a public key” (Equipo editorial de IONOS, 2022; own translation). It is important to know this because, in GPG, this model allows anyone to send you secure information using your public key, but only you can read it. 

According to Vikash (2024), the fundamental difference between an encrypted message and a signed one depends on its functionality: 

Encryption protects the confidentiality of data, ensuring that only the intended
recipient can access the content. Signing verifies the authenticity and integrity of the 	
data, confirming the sender’s identity and that the message has not been altered. 

This means that, while encryption acts as a shield of confidentiality, transforming the 
message into a code that only the recipient can decipher; the digital signature functions 
as a seal that guarantees authenticity and integrity. Together, they ensure that communication 
is private, truthful, and resistant to manipulation. 

2. Compare ProtonMail, Gmail, and Outlook in terms of: 

(a) Encryption at rest. 

ProtonMail utilizes a “Zero Access” system, which means that “not even Proton can read your messages, providing protection against external threats and potential government data requests” (Baumgarten et al., 2025; own translation). This means that the emails stored on their servers are encrypted with a key derived from the user's password that the provider does not know and cannot reset. In contrast, Gmail and Outlook encrypt data on their hard drives, but “retain the ability to access the content of your emails, a fundamental architectural difference” (Baumgarten et al., 2025; own translation). This would allow them to access the content if necessary for internal processes or legal requirements. 

(b) Encryption in transit. 

Unlike Gmail and Outlook, which rely almost exclusively on TLS for transit, ProtonMail adds layers of identity validation that distinguish it from the competition. According to its technical documentation, "ProtonMail uses digital signatures to verify email addresses, helping to prevent phishing attacks. This feature adds an extra layer of security by confirming the authenticity of the sender" (Atomic Mail, 2025). By using digital signatures to validate addresses, the system confirms the sender's authenticity, creating a technical barrier that prevents identity spoofing attacks that traditional providers fail to stop as effectively. 

(c) End-to-end encryption (E2EE). 

La diferencia crucial es que normalmente “Gmail no utiliza cifrado de extremo a extremo. En su lugar, guarda su propia clave de su bandeja de entrada para poder escanear sus mensajes” (Proton Mail, 2025). Esta falta de cifrado de extremo a extremo revela que la prioridad del servicio es la funcionalidad y el procesamiento de datos sobre la privacidad absoluta, permitiendo que el proveedor mantenga un acceso de la información.  

Similarmente, aunque Outlook tiene mayores opciones de cifrado “no puede garantizar la total privacidad de tus correos” (Proton Mail, 2025). En un entorno corporativo, la seguridad suele ser perimetral pero no privada; es decir, protegen el mensaje de extraños, pero el proveedor sigue teniendo la capacidad técnica de entregar tus correos si la ley lo exige.   

Por otro lado, ProtonMail “protege todos sus mensajes de correo electrónico y contactos con cifrado de extremo a extremo y cifrado de acceso cero. Esto significa que solo usted tiene acceso a su bandeja de entrada” (Proton Mail, 2025). Esta arquitectura de traslada la soberanía de los datos totalmente al usuario, eliminando el factor de confianza en la empresa y reemplazándolo por una certeza donde el proveedor es técnicamente incapaz de espiarte. 

The crucial difference is that normally “Gmail does not use end-to-end encryption. Instead, it keeps its own key to your inbox so it can scan your messages” (Proton Mail, 2025; own translation). This lack of end-to-end encryption reveals that the service's priority is functionality and data processing over absolute privacy, allowing the provider to maintain access to the information. 

Similarly, although Outlook has more encryption options, “can’t guarantee your emails are completely private” (Proton Mail, 2025). In a corporate environment, security is usually perimeter-based but not private; that is, they protect the message from strangers, but the provider still has the technical capacity to hand over your emails if the law requires it. 

On the other hand, ProtonMail “protects all your email messages and contacts with end-to-end encryption and zero-access encryption. This means that only you have access to your inbox” (Proton Mail, 2025; own). This architecture fully transfers data sovereignty to the user, eliminating the factor of trust in the company and replacing it with a certainty where the provider is technically incapable of spying on you. 

(d) Privacy policies and data access by the provider. 

Unlike ProtonMail, which applies "zero-access" encryption to protect the user, Gmail and Outlook operate under models that allow data visibility by third parties. In the case of Google, there is a structural vulnerability in its ecosystem: “Google also allows developers who build apps that use the Gmail Application Programming Interface (API) to read the contents of your private emails” (z3r0trust, 2025). For its part, Outlook presents a similar risk by massively integrating productivity applications and third-party add-ons into its business environment; although its focus is less advertising-oriented than Google's, its privacy policies allow for telemetry and technical access by the provider for the maintenance of cloud services, which means that in both providers privacy is delegable and depends on the ethics of external developers. 

(e) Legal jurisdiction. 

	The physical location of servers defines the legal framework that protects data. ProtonMail operates under the strict jurisdiction of Switzerland, which allows it to comply with high-standard international requirements. According to the Mailbird blog, “Proton Mail’s Swiss jurisdiction and zero-access encryption architecture directly address these requirements, potentially eliminating the need for additional encryption tools” (Baumgarten et al., 2025; own translation). This simplifies the security architecture by eliminating the need for external software, ensuring that privacy is a native feature of the system and not an additional patch. 

In contrast, Gmail and Outlook are subject to U.S. regulations that prioritize international judicial cooperation. According to the U.S. Department of Justice, the CLOUD Act was designed to allow foreign partners to obtain “direct access to this electronic evidence, wherever it happens to be located, in order to fight serious crime and terrorism” (Criminal Division: U.S Department of Justice, 2023). This legislation represents a new paradigm that obliges U.S.-based providers to deliver data even if it is stored on servers outside their territory. 


3. What is the PKI model based on Certificate Authorities (CA)? Cite 2 advantages and 2 disadvantages compared to the Web of Trust (WoT). 

The Public Key Infrastructure (PKI) is a “security framework that uses cryptographic key pairs and digital certificates to authenticate identities” (Entrust, 2026; own translation). Unlike decentralized models, PKI centralizes trust in the Certificate Authority (CA), a “trusted third-party organization that creates and issues digital certificates” (Entrust, 2026; own translation), validating identities through a superior mathematical hierarchy instead of mutual knowledge between users. 

Compared to the Web of Trust (WoT), PKI stands out for its scalability, allowing “configuration changes can be done within your premises and on your schedule.” (Monton, 2021). By possessing an “issuance process is within your control, and you are not limited when accessing the cloud” (Monton, 2021), organizations achieve an operational autonomy that dispenses with the manual signatures of the PGP model, facilitating immediate responses to incidents. 

However, this centralization forces the entity to “manage possible risks and problems that may arise” (Monton, 2021) by constituting a single point of failure. Furthermore, it entails “hidden costs of on-premise PKI such as software” (Monton, 2021). Ultimately, the free and community resilience of the WoT is sacrificed for a corporate efficiency that, if not managed with rigor, results in a costly system vulnerable to attacks directed at the core of trust. 


4. Research Question: What rights do the GDPR (EU) and LOPDP (Ecuador) grant citizens regarding email and digital surveillance?

Both the European General Data Protection Regulation (GDPR) and the Organic Law on the Protection of Personal Data of Ecuador (LOPDP) establish high standards for digital privacy, specifically concerning email communications and digital surveillance. Under the GDPR (Articles 15-17), European citizens are granted the right to access their data, rectify inaccuracies, and the "right to be forgotten" (erasure), which allows them to request the permanent deletion of their personal information. Similarly, the LOPDP (Articles 13-16) guarantees Ecuadorian citizens the rights of access, rectification, and erasure, while also emphasizing the right to objection, allowing individuals to refuse the processing of their data for specific purposes.

Regarding surveillance, the GDPR (Recital 158) mandates that all electronic communications must remain confidential, requiring a clear, proportional, and transparent legal basis for any monitoring. In Ecuador, the LOPDP Regulation (Article 8) establishes that data processing must strictly adhere to the principle of confidentiality, explicitly guaranteeing the security of private communications against unauthorized interception. Additionally, both frameworks protect data portability (Art. 20 GDPR / Art. 17 LOPDP), ensuring users can receive and transfer their emails in structured, machine-readable formats. Finally, they both mandate the security of processing (Art. 32 GDPR / Art. 37 LOPDP), requiring providers to implement advanced technical measures like encryption to guarantee the integrity and confidentiality of user information.


5. What is email metadata? Why does content encryption not protect metadata, and what are the implications for privacy? 

	Email metadata is defined as the “collection of technical and contextual attributes generated as an email is created, transmitted, processed, and stored across mail systems” (Murugan, 2026). This data functions as the message's "envelope," containing the essential logistical information for communication to be possible across the network. 

However, end-to-end encryption, while protecting the content, is unable to hide this routing information because intermediate servers require reading it to deliver the message. As detailed in the research by Mailbird (2025; own translation), this exposure “allows for sophisticated profiling that can reconstruct what researchers call a 'social graph'—a comprehensive visualization of your entire communication network.” This technical reality teaches us that the insecurity of metadata is not a programming error, but a design limitation of the internet itself. As engineers, we must understand that encryption is only a layer of content protection and not a solution for total anonymity. 

The most critical vulnerability resides in the accumulation and analysis of this information, since “advertisers, intelligence agencies, and data brokers have developed sophisticated techniques to extract behavioral information solely from metadata” (Mailbird, 2025; own translation). This metadata allows external entities to identify routines, locations, and contacts without the need to access the body of the email. This implies that it enables predictive spying for those who manage the network infrastructure. 

