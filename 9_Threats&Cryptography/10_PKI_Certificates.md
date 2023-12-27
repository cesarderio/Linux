# Acquiring a PKI Certificate for a Linux Host from a Private CA

<br>

## Overview

This demo demonstrates acquiring a Public Key Infrastructure (PKI) certificate for a web server hosted on a Linux system. The process involves generating a Certificate Signing Request (CSR) and obtaining a certificate from a private Certificate Authority (CA) established on the same server.

<br>

## Steps for Acquiring PKI Certificate

1. **Check CA Certificate and Key:**
   - Navigate to the easy-rsa directory and check the presence of CA certificate (`ca.crt`) and private key (`ca.key`).

2. **Install OpenSSL:**
   - Command: `sudo apt install openssl`
   - OpenSSL is used for generating key pairs and certificate requests.

3. **Create Certificate Signing Request:**
   - Create a directory for the CSR (e.g., `mkdir csr`).
   - Generate an RSA key pair: `openssl genrsa -out ubuntu1server.key`.
   - Generate the CSR: `openssl req -new -key ubuntu1server.key -out ubuntu1server.req`.
   - Fill in the details such as country, common name (e.g., `www.quick24x7.com`), and admin email.

4. **View and Secure Private Key:**
   - The generated private key (`ubuntu1server.key`) should be securely stored as it is crucial for certificate operation.

5. **Submit CSR to CA:**
   - Transfer the CSR file (`ubuntu1server.req`) to the CA server for certificate issuance.
   - This can be done via email, web form, or secure copy, depending on the setup.

6. **CA Processing of CSR:**
   - On the CA server (or the same machine if CA is local), import the CSR using easy-rsa scripts.
   - Command: `./easyrsa import-req /path/to/ubuntu1server.req ubuntu1server`.
   - Sign the imported request to issue the certificate: `./easyrsa sign-req server ubuntu1server`.

7. **Confirmation of Certificate Issuance:**
   - Confirm the signing of the certificate, including verifying details such as validity period and subject.
   - Enter the passphrase for the CA's private key to authorize the signing process.
   - The certificate is certified for a specific period (e.g., over two years).

8. **Retrieve Issued Certificate:**
   - Navigate to the `issued` directory under `pki` to find the issued certificate file (`Ubuntu1server.crt`).

9. **Conclusion:**
   - The issued certificate (`Ubuntu1server.crt`) is now available for use, for example, to enable HTTPS binding on a web server.
   - The process demonstrates a command-line approach to acquiring a PKI certificate from a private CA on a Linux host.

<br>

## Additional Notes

- It's crucial to securely handle the private key and the issued certificate.
- The CSR details should match the intended use and identity of the server or entity for which the certificate is requested.
- The demonstration outlines a self-contained process on a single server but can be adapted to different environments where the CA and requesting server are separate.
