Test 1 (AOC) version
Question 1
**a)** You have been engaged as part of a cybersecurity evaluation exercise for a multinational oil and gas enterprise operating highly integrated Industrial Control Systems (ICS), Supervisory Control and Data Acquisition (SCADA) networks, and secure cloud-linked telemetry infrastructure connecting offshore production platforms, subsea pipelines, and onshore refinery control centers. The organization relies on real-time encrypted data exchange between distributed control nodes, programmable logic controllers (PLCs), and centralized security operations centers (SOC). Given the high-risk environment—including potential Advanced Persistent Threat (APT) activity targeting operational technology (OT) systems—you are expected to demonstrate a clear technical understanding of fundamental cryptographic concepts as applied in securing industrial communication protocols such as **TLS-secured OPC UA**, **IPsec tunnels**, and **AES-encrypted** telemetry streams. As part of this assessment, define and explain the **_nine cryptographic and information security terms_** in a technically grounded manner, referencing their role in securing machine-to-machine and system-to-system communications in this environment as depicted by Figure Q1a (9.5 Marks)
![[Picture.png]]{width=692}
**ANSWER**

a. The technically grounded definitions of the requested cryptographic terms with notes on their role in securing machine-to-machine (M2M) and system-to-system communications in ICS/SCADA/OT environments (TLS-secured OPC UA, IPsec tunnels, AES telemetry, etc.). Definitions (term – short technical definition = OT role) **(0.5 Mark)**

i. **Cryptanalysis (code-breaking)**     a. **Definition:** The study and practice of analyzing cryptographic systems to find weaknesses or discover secret information (keys, plaintext) without authorized access. Techniques include mathematical attacks, side-channel analysis, brute-force, and protocol-level exploitation. **(0.5 Mark)**
c. **OT role:** Used offensively (by APTs) to break confidentiality/integrity of telemetry or control commands, and defensively (by security teams) to test cipher/key strength, detect weak key reuse in PLC firmware or broken TLS implementations in OPC UA stacks. **(0.5 Mark)**

ii. **Key**     a. **Definition:** Secret (or private/public) data used by cryptographic algorithms to control transformation between plaintext and ciphertext. Keys can be symmetric (same key encrypt/decrypt) or asymmetric (public/private key pair). **(0.5 Mark)**     
b. **OT role:** Protects device identities and sessions (AES keys for telemetry, IPsec PSKs or IKE-derived keys, TLS private keys for OPC UA). Key compromise = loss of confidentiality/integrity for PLC commands and sensor data. **(0.5 Mark)**

iii. **Cipher**     a. **Definition:** The algorithm or mathematical procedure that, using a key, transforms plaintext to ciphertext and vice versa (e.g., AES, ChaCha20, RSA). **(0.5 Mark)** 
b. **OT role:** Provides the actual confidentiality/integrity primitives used in tunnels and session encryption (AES-GCM for telemetry, ChaCha20-Poly1305 in resource-constrained edge gateways). **(0.5 Mark)**

iv. **Plaintext**     a. **Definition:** Original readable data before encryption (control commands, sensor values, configuration payloads). **(0.5 Mark)**     
b. **OT role:** SCADA commands, telemetry, alarms — must be protected in transit and at rest. Exposure can permit sabotage, spoofing, or safety incidents. **(0.5 Mark)**

v. **Cryptology**     a. **Definition:** The broader scientific field encompassing cryptography (constructing secure systems) and cryptanalysis (breaking them). **(0.5 Mark)**     
b. **OT role:** Guides design/assessment of secure communication stacks for ICS: selection of primitives, key management, threat modelling against APTs. **(0.5 Mark)**