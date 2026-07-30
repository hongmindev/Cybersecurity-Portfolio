# Concept Note: Non-Repudiation (CompTIA Security+ SY0-701)

## 1. Objective
Understand the cryptographic principles of non-repudiation, how hashing provides proof of integrity, and how digital signatures establish proof of origin so senders cannot deny transmitting a message or document.

## 2. Core Concepts & Definitions
* **Non-Repudiation:** A legal and cryptographic guarantee that provides proof of data integrity and authentication, ensuring a party cannot successfully deny sending a message or signing a transaction (similar to a handwritten physical signature).
* **Proof of Integrity:** The ability to verify that data has remained accurate, consistent, and unaltered since it was originally transmitted.
* **Proof of Origin (Authentication):** The ability to confirm without a doubt *who* sent a specific piece of data or message.

## 3. Technical Mechanisms & Workflow
1. **Hashing (Integrity):**
   * A hashing algorithm creates a short string of text (a message digest or fingerprint) based on plaintext. 
   * Even a microscopic change to the file alters the resulting hash completely, signaling that the data has been modified.
   * *Limitation:* While a hash proves data wasn't changed, it does *not* tell you who sent it.
2. **Digital Signatures (Non-Repudiation & Origin):**
   * Combines a hash with asymmetric cryptography to provide both integrity and authenticity.
   * **The Sender's Process (e.g., Alice):**
     1. Creates a hash of the plaintext message.
     2. Encrypts that hash using her **private key** (which only she possesses).
     3. Sends both the plaintext and the encrypted hash (digital signature) to the recipient.
   * **The Recipient's Process (e.g., Bob):**
     1. Uses the sender's **public key** to decrypt the digital signature back into the original hash.
     2. Runs the received plaintext through the exact same hashing algorithm to generate a fresh hash.
     3. Compares the two hashes: if they match, it proves the data hasn't been tampered with *and* that it definitely came from the holder of the matching private key.

## 4. Why This Matters (Security Perspective)
* **For Security Operations & Legal Compliance:** Non-repudiation is critical for secure communications, financial transactions, electronic contracts, and log auditing. If an admin executes an unauthorized command or a user signs off on a transaction, non-repudiation ensures they cannot falsely claim they didn't do it.
* **For Certification & Practice:** The Security+ exam frequently tests your understanding of asymmetric key pairs (public vs. private keys) and how digital signatures achieve non-repudiation.

## 5. Lessons Learned
Relying on simple data transmission is inherently risky because data can be intercepted, altered, or spoofed. By combining hashing algorithms with asymmetric encryption, systems can automatically enforce strict accountability and trust without manual intervention.

---
[Non-repudiation - CompTIA Security+ SY0-701 - 1.2](https://youtu.be/XxnCxPEllMg)
