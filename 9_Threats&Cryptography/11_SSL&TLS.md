# HTTP Network Encryption: SSL vs TLS

<br>

## Overview

This content discusses the use of Secure Sockets Layer (SSL) and Transport Layer Security (TLS) protocols for HTTP network encryption, emphasizing the preference for TLS over the deprecated SSL.

<br>

## Key Points

1. **SSL Protocol Suite:**
   - Developed by Netscape in the early 1990s.
   - Deprecated due to vulnerabilities.
   - Should not be used; can be disabled on both servers and clients.

2. **TLS Protocol Suite:**
   - Designed to supersede SSL.
   - Use at least version 1.2, ideally version 1.3.
   - Enabled on HTTPS web servers and can be configured in web browser settings.
   - More secure and up-to-date compared to SSL.

3. **Certificate Nomenclature:**
   - Often referred to as SSL certificates, though they are PKI certificates.
   - Can be used with various network security protocols like SSL, TLS, IPsec.

4. **TLS Communication Process:**
   - Client contacts server on HTTPS port, presents supported ciphers.
   - Server and client agree on a cipher suite.
   - Server sends its PKI certificate to the client.
   - Client verifies certificate validity, generates a session key, encrypts it with the server's public key, and sends it back.
   - Server decrypts the session key with its private key for secure communication.

5. **Capturing TLS Traffic:**
   - Appears scrambled in tools like Wireshark.
   - TLS header and encrypted data are visible, confirming encryption.

6. **Cloud-Based PKI Certificates:**
   - Microsoft Azure Key Vault can create/generate new PKI certificates.
   - Certificates can be used for cloud services or on-premises servers.
   - Includes options like self-signed certificates and configurable validity periods.

7. **Web App HTTPS Binding in Cloud:**
   - Can host web apps on Linux platforms in the cloud (e.g., Azure).
   - HTTPS prefix in URLs indicates secure connections using PKI certificates.

<br>

## Additional Insights

- **SSL vs TLS Terminology:** The persistent use of "SSL certificate" terminology is a misnomer since SSL is outdated, and TLS is the preferred encryption protocol.
- **Cloud and Linux Interplay:** Cloud services, like Azure's web app hosting, often run on Linux, highlighting the significance of Linux in cloud-based solutions.
- **Importance of Up-to-Date Protocols:** Staying current with TLS versions is crucial for maintaining robust network security.

<br>

## Conclusion

Understanding the differences between SSL and TLS is vital for network security, with TLS being the recommended protocol for encrypted HTTP communication. The integration of PKI certificates in both on-premises and cloud environments, especially in Linux-based systems, plays a significant role in securing web applications and data transmission.
