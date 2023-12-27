# Public Key Infrastructure (PKI) Explained

<br>

## Overview
Public Key Infrastructure (PKI) is a crucial aspect of digital security, consisting of a hierarchy of digital certificates. It establishes a chain of trust, ensuring that certificates from a trusted Certificate Authority (CA) are inherently reliable.

<br>

## Chain of Trust in PKI

- Root of Trust: Trust in a high-level CA implies trust in all subordinate certificates issued by it.
- Hierarchical Structure: PKI is structured with a root CA at the top and possibly several subordinate CAs under it.

<br>

## Certificate Authorities (CAs)

1. **Public Trusted CAs**:
   - Widely recognized and automatically trusted by most operating systems.
   - Used for public applications like HTTPS websites.

2. **Private Internal Untrusted CAs**:
   - Organization-specific and not inherently trusted by external systems.
   - Requires manual trust establishment on devices.
   - Common in large organizations with multiple internal CAs for different departments or regions.

<br>

## Configuring a Private CA

- Can be set up on various platforms, including Windows Server and public cloud services like AWS.
- Starts with establishing a root CA, followed by optional subordinate CAs.
- Usage varies based on organizational needs.

<br>

## PKI Hierarchy Visualization

- **Root CA**: At the top of the hierarchy, often taken offline for security.
- **Subordinate CAs**: Issue certificates and manage specific segments like regional or departmental needs.
- **Certificates**: Issued by the CAs, containing encryption details, usage constraints, subject information, and validity period.

<br>

## Certificate Templates

- Templates dictate the type of encryption, signing algorithms, and usage constraints (e.g., email encryption, file system encryption).

<br>

## PKI Certificate Components

- **Subject Name**: Identifies the entity (e.g., website's FQDN, user email).
- **Issuer**: The name of the CA that issued the certificate.
- **Digital Signature**: The CA's signature for authenticity.
- **Validity Period**: Issue and expiry dates.
- **Public Key**: Included in the certificate.
- **Private Key**: Stored securely, not within the certificate.
- **Other Attributes**: Additional details as required.

<br>

## Importance of PKI

- Establishes a secure framework for digital communications and transactions.
- Ensures integrity and trustworthiness of digital certificates.
- Facilitates secure data exchange, authentication, and encryption.

<br>

## Conclusion

PKI is essential for maintaining digital security and trust in various online interactions. Its hierarchical structure, with trusted CAs at the core, ensures that certificates are reliable and secure, playing a vital role in modern cybersecurity practices. Whether through public CAs for widespread use or private CAs for internal control, PKI remains a fundamental aspect of digital security infrastructure.
