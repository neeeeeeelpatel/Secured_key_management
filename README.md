# Secure Key Management System (KMS)

## Overview  
This project focuses on building a **Secure Key Management System (KMS)** to facilitate both symmetric and asymmetric encryption. The system ensures **robust security** by implementing key distribution, secure storage, key exchange, and revocation mechanisms.  

## Core Functionalities  
1. **Centralized Key Management** – AES encryption keys are **generated and maintained in a centralized system** to ensure secure access and controlled distribution.  
2. **Public Key Infrastructure (PKI) Simulation** – Implements **RSA key pair generation** to support asymmetric encryption.  
3. **Secure Key Generation & Storage** – Uses cryptographic libraries to create and store keys **using strong random number generation techniques**.  
4. **Secure Key Exchange** – **Diffie-Hellman (DH) key exchange** is implemented to establish **ephemeral session keys**, enhancing forward secrecy.  
5. **Key Revocation** – The system **enables key deletion** to prevent unauthorized access in case of compromise.  

---

## Features  

### **1. Symmetric Encryption (AES)**  
- **256-bit AES key generation** for secure encryption.  
- Uses **Cipher Block Chaining (CBC) mode** with PKCS7 padding for data encryption and integrity.  

### **2. Asymmetric Encryption (RSA)**  
- **2048-bit RSA key pair creation** for secure message exchange.  
- RSA encryption and decryption are implemented **using PKCS1v15 padding**.  

### **3. Diffie-Hellman Key Exchange**  
- Generates **ephemeral DH keys** to securely derive session keys.  
- Provides **forward secrecy**, ensuring that past communications remain secure even if a key is compromised.  

### **4. Key Revocation**  
- The system allows **on-demand key deletion** to mitigate unauthorized use of compromised keys.  

---

## System Requirements  
- **Python 3.6+**  
- **cryptography library** (to enable cryptographic operations)  

---

## Installation Steps  

### **Step 1: Clone the Repository**  
```bash
git clone https://github.com/yourusername/secure-key-management.git
cd secure-key-management
```  

### **Step 2: Install Dependencies**  
```bash
pip install cryptography
```  

---

## Running the System  

To execute the system, run the main Python script:  

```bash
python secure_key_mgmt.py
```  

This will trigger **predefined test cases**, including:  
 - AES encryption and decryption verification  
 - RSA encryption and decryption validation  
 - Diffie-Hellman key exchange execution  
 - Key revocation test (ensuring decryption fails post-revocation)  

---

## Code Structure  

### **Main Class: SecureKeyManagementSystem**  
This class handles various cryptographic operations, including:  

🔹 **Symmetric Key Operations**  
- `generate_aes_key()`: Creates a secure AES key.  
- `encrypt_with_aes()`: Encrypts data using AES.  
- `decrypt_with_aes()`: Decrypts AES-encrypted data.  

🔹 **Asymmetric Key Operations**  
- `generate_rsa_key_pair()`: Generates an RSA key pair.  
- `encrypt_with_rsa()`: Encrypts data using RSA.  
- `decrypt_with_rsa()`: Decrypts RSA-encrypted data.  

🔹 **Key Exchange Mechanism**  
- `generate_diffie_hellman_key()`: Establishes a **secure shared key** using DH key exchange.  

🔹 **Key Revocation Mechanism**  
- `key_revocation()`: Removes compromised keys to prevent unauthorized decryption.  

---

## Testing & Demonstration  

The system includes automated test cases to demonstrate:  
- Secure encryption & decryption using **AES and RSA**.  
- Safe key exchange via **Diffie-Hellman**.  
- Effective key revocation handling.  

---

## Security Measures  

🔹 **Preventing Man-in-the-Middle (MITM) Attacks**  
- While this system **simulates** a PKI environment, a real-world deployment would incorporate **a trusted Certificate Authority (CA)** to verify public keys.  
- **TLS/SSL encryption** would be used in an actual implementation to prevent unauthorized interception.  

🔹 **Forward Secrecy Implementation**  
- **Ephemeral Diffie-Hellman keys** ensure that past encrypted messages remain safe, even if long-term keys are compromised.  

🔹 **Key Revocation Strategy**  
- The system provides a **simple but effective key deletion process**, mitigating risks associated with compromised keys.  

---

## Conclusion  
This **Secure Key Management System** is designed to handle cryptographic key management effectively, incorporating **AES and RSA encryption, Diffie-Hellman key exchange, and a structured revocation process**. Future enhancements could include **certificate-based authentication and advanced key lifecycle management**.  

---
