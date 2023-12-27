# Public Key Infrastructure (PKI) Certificate Lifecycle

<br>

## Overview

PKI Certificate Lifecycle involves various stages from the creation to the potential expiry or renewal of a digital certificate. Understanding this lifecycle is crucial for maintaining the security and validity of certificates.

<br>

## Stages of PKI Certificate Lifecycle

1. **Certificate Signing Request (CSR):**
   - The lifecycle starts with generating a CSR.
   - Involves creating a public-private key pair.
   - The CSR is then submitted to a Certificate Authority (CA) for approval.

2. **Issuance:**
   - The CA conducts due diligence before issuing the certificate.
   - The certificate can be issued manually or automated, depending on the system.

3. **Use:**
   - Post-issuance, the certificate is installed on a device or attached to an email, VPN, etc.
   - It can exist in various forms like files or on smart cards.

4. **Revocation:**
   - A certificate can be revoked if compromised, e.g., due to device loss.
   - Revocation is based on the certificate’s unique serial number.
   - Devices check an updated Certificate Revocation List (CRL) or use Online Certificate Status Protocol (OCSP) for revocation status.

5. **Renewal/Expiry:**
   - Prior to expiry, a certificate can be renewed.
   - If expired, it cannot be used and must be reissued.

<br>

## Key Aspects of PKI Certificates

- **Certificate Signing Request (CSR):** Initial step for requesting a new PKI certificate.
- **Public and Private Keys:** The private key is stored separately and securely.
- **Details in CSR:** May include common name, organization name, admin's email, etc.
- **Usage Scenarios:** Certificates can be user-specific or device-specific.
- **Wildcard Certificates:** Useful for securing multiple servers within the same domain.
- **Extended Domain Validation:** Enhanced CA due diligence for specific uses like e-commerce.
- **Code Signing Certificates:** Essential for software developers for app store submissions.

<br>

## Trusted Root Certification Authorities

- Certificates from public trusted CAs are automatically recognized by most devices.
- For private internal CAs, root certificates must be imported to devices for trust establishment.

<br>

## Revocation Mechanisms

1. **Certificate Revocation List (CRL):**
   - A list of revoked certificates downloaded by services to verify trust.

2. **Online Certificate Status Protocol (OCSP):**
   - Checks the validity of certificates in real-time without downloading the entire CRL.

<br>

## Conclusion

The PKI certificate lifecycle is a comprehensive process that ensures the secure and trusted use of digital certificates. It covers everything from the initial request to the end-of-life of a certificate, encompassing issuance, usage, and potential revocation. Understanding and managing this lifecycle is vital for maintaining digital security and trust within an organization.
