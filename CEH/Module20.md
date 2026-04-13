# Module 20: Cryptography

## 1. Introduction to Cryptography

**Definition:**  
Cryptography is the science of protecting information by converting it into an unreadable format using algorithms and keys.

**Core Security Goals:**  
- **Confidentiality** — Prevent unauthorized access.  
- **Integrity** — Ensure data is not altered.  
- **Authentication** — Verify identity.  
- **Non-repudiation** — Prevent denial of actions.  

**Basic Terms:**  
- **Plaintext** — Original readable data.  
- **Ciphertext** — Encrypted data.  
- **Encryption** — Plaintext to ciphertext.  
- **Decryption** — Ciphertext to plaintext.  
- **Key** — Secret value used in the algorithm.  

**Example:**  
A password is encrypted before transmission instead of being sent in plain text.

---

## 2. Government Access to Keys (GAK)

**Definition:**  
A system where governments can access encrypted data through backdoors or escrowed keys.

**Explanation:**  
This was introduced for law enforcement surveillance and key recovery.

**Security Concerns:**  
- Weakens encryption.  
- Can be abused.  
- Creates a single point of failure.  

**Key Point:**  
GAK is controversial because it breaks the trust model of end-to-end encryption.

---

## 3. Ciphers

**Definition:**  
A cipher is an algorithm used to encrypt and decrypt data.

**Types:**  
- **Substitution Cipher** — Replaces letters or symbols.  
- **Transposition Cipher** — Rearranges characters.  

**Modern Ciphers:**  
- AES  
- DES  
- RSA  

---

## 4. Symmetric Encryption Algorithms

**Definition:**  
The same key is used for both encryption and decryption.

**Examples:**  
- AES  
- DES  
- 3DES  

**Working:**  
Sender encrypts with a shared key, and the receiver decrypts with the same key.

**Advantages:**  
- Fast.  
- Efficient for large data.  

**Disadvantages:**  
- Key distribution problem.  

**Example:**  
Encrypting files using AES-256.

---

## 5. Asymmetric Encryption Algorithms

**Definition:**  
Uses two keys: a public key for encryption and a private key for decryption.

**Examples:**  
- RSA  
- ECC  

**Advantages:**  
- Secure key exchange.  

**Disadvantages:**  
- Slower than symmetric encryption.  

**Example:**  
HTTPS uses asymmetric encryption during key exchange.

---

## 6. Message Digest Functions

**Definition:**  
A one-way function that converts input into a fixed-length hash.

**Properties:**  
- Irreversible.  
- Fixed-size output.  
- Small input changes produce different hashes.  

**Examples:**  
- MD5  
- SHA-1  
- SHA-256  

**Use Cases:**  
- Password storage.  
- File integrity checking.  

---

## 7. Message Digest Calculators

**Definition:**  
Tools used to compute hashes.

**Examples:**  
- `md5sum`  
- `sha256sum`  
- HashCalc  

---

## 8. Multilayer Hashing

**Definition:**  
Applying multiple layers of hashing to strengthen password protection.

**Example:**  
Hashing a password multiple times before storing it.

---

## 9. Hardware-Based Encryption

**Definition:**  
Encryption performed using dedicated hardware.

**Examples:**  
- TPM  
- HSM  

**Advantages:**  
- Faster processing.  
- More secure and tamper-resistant.  

---

## 10. Quantum Cryptography

**Definition:**  
Uses quantum mechanics to secure communication.

**Example:**  
Quantum Key Distribution (QKD).

**Security Benefit:**  
Eavesdropping can be detected immediately.

---

## 11. Other Encryption Techniques

**Examples:**  
- Steganography  
- Homomorphic encryption  
- Format-preserving encryption  

---

## 12. Cipher Modes of Operation

**Definition:**  
Modes determine how encryption algorithms process blocks of data.

**Types:**  
- **ECB** — Insecure.  
- **CBC**  
- **CFB**  
- **OFB**  
- **CTR**  

**Important:**  
ECB reveals patterns and is not secure for sensitive data.

---

## 13. Authenticated Encryption Modes

**Definition:**  
These provide both confidentiality and integrity.

**Examples:**  
- GCM  
- CCM  

---

## 14. Cryptography Tools

**Tools:**  
- OpenSSL  
- GPG  
- VeraCrypt  
- Hashcat  

---

## 15. Applications of Cryptography

**Uses:**  
- Secure communication over HTTPS.  
- Digital signatures.  
- VPNs.  
- Email encryption.  

---

## 16. Public Key Infrastructure (PKI)

**Definition:**  
A framework for managing digital certificates and public/private keys.

**Components:**  
- Certificate Authority (CA)  
- Registration Authority (RA)  
- Digital certificates  

---

## 17. Certificate Authorities

**Definition:**  
Trusted entities that issue and sign digital certificates.

**Examples:**  
- DigiCert  
- Let’s Encrypt  

---

## 18. CA-Signed vs Self-Signed Certificates

| Feature | CA-Signed | Self-Signed |
|---------|-----------|-------------|
| Trust | High | Low |
| Usage | Public websites | Testing and internal use |

---

## 19. Digital Signature

**Definition:**  
A cryptographic method used to verify authenticity and integrity.

**Working:**  
Hash the message, encrypt the hash with the private key, and verify using the public key.

---

## 20. SSL

**Definition:**  
A protocol used for secure communication.

**Status:**  
Deprecated and replaced by TLS.

---

## 21. TLS

**Definition:**  
Transport Layer Security is the modern secure protocol used in HTTPS.

**Function:**  
- Encryption.  
- Authentication.  

---

## 22. Cryptography Toolkits

**Libraries:**  
- OpenSSL  
- Bouncy Castle  

---

## 23. PGP

**Definition:**  
Pretty Good Privacy is an encryption program for email and files.

**Features:**  
- Hybrid encryption.  
- Digital signatures.  

---

## 24. GPG

**Definition:**  
GNU Privacy Guard is the open-source version of PGP.

---

## 25. Web of Trust

**Definition:**  
A trust model where users validate each other’s keys and identities.

---

## 26. Email Encryption

**Methods:**  
- Outlook encryption.  
- Mac Mail encryption.  
- OpenPGP.  

**Tools:**  
- ProtonMail  
- GPG tools  

---

## 27. Disk Encryption

**Definition:**  
Encrypting an entire storage device.

**Examples:**  
- BitLocker  
- FileVault  
- LUKS  

---

## 28. Blockchain

**Definition:**  
A distributed ledger secured using cryptography.

**Features:**  
- Immutability.  
- Decentralization.  

---

## 29. Cryptanalysis

**Definition:**  
The study of breaking cryptographic systems.

---

## 30. Cryptanalysis Methods

- Ciphertext-only.  
- Known plaintext.  
- Chosen plaintext.  
- Chosen ciphertext.  

---

## 31. Cryptography Attacks

**Common Attacks:**  
- **Brute Force** — Try all possible keys.  
- **Rainbow Table** — Uses precomputed hashes.  
- **Hash Collision** — Two inputs produce the same hash.  
- **Padding Oracle** — Exploits padding errors.  
- **Side-Channel** — Uses timing or power usage.  
- **DUHK** — Targets hardcoded keys in IoT devices.  
- **DROWN** — Exploits SSLv2 weaknesses.  
- **Related-Key** — Studies relationships between keys.  

---

## 32. Blockchain Attacks

**Examples:**  
- 51% attack.  
- Double spending.  

---

## 33. Quantum Computing Risks

**Impact:**  
Quantum computing can break RSA and weaken some existing encryption methods.

---

## 34. Cryptanalysis Tools

**Tools:**  
- Hashcat  
- John the Ripper  

---

## 35. MD5 Decryption Tools

**Methods:**  
- Online hash crackers.  
- Rainbow tables.  

---

## 36. Cryptography Countermeasures

**Best Practices:**  
- Use strong algorithms such as AES-256 and SHA-256.  
- Avoid MD5 and SHA-1.  
- Use proper key management.  
- Implement MFA.  

**Defense Against Attacks:**  
- Salt passwords.  
- Use key stretching.  
- Use secure protocols like TLS 1.3.
