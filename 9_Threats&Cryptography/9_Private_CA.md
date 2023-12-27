# Deploying a Private Certificate Authority (CA) on a Linux Host

<br>

## Overview

Deploying a private Certificate Authority (CA) is essential for managing the Public Key Infrastructure (PKI) hierarchy within an organization. This demo outlines the process of setting up a private CA using easy-rsa on a Linux host.

<br>

## Steps to Deploy Private CA

1. **Install easy-rsa:**
   - Command: `sudo apt install easy-rsa`
   - Provides tools for managing the PKI hierarchy.

2. **Create and Link Directories:**
   - Make a directory named `easy-rsa` in the home directory.
   - Create symbolic links to the files in `/usr/share/easy-rsa/` to the new directory.

3. **Adjust Permissions:**
   - Command: `sudo chmod 700` for permission adjustments.
   - Change the ownership to the current user using `sudo chown -R`.

4. **Initialize PKI Directory:**
   - Navigate to `easy-rsa` directory.
   - Run `./easy-rsa` script to initialize a fresh PKI.
   - Confirm the initialization with `yes`.

5. **Edit Variables File:**
   - Edit the `vars` file inside the `pki` directory.
   - Set variables for country, province, city, organization, admin email, and OU.

6. **Build CA:**
   - Run `./easyrsa build-ca` to create the CA.
   - Set and verify the CA key passphrase.
   - Provide a common name for the CA host.

7. **Verify CA Files:**
   - In the `pki` directory, you find the CA certificate file (`ca.crt`).
   - The `private` directory contains the CA private key file (`ca.key`).

8. **Key Management:**
   - The `ca.key` file (private key) should be safeguarded as it's crucial for security.
   - The `ca.crt` file (public key certificate) can be distributed for establishing trust.

<br>

## Conclusion

With this setup, a private CA on a Linux host is now operational, forming the backbone of the internal PKI hierarchy. This CA can issue and manage certificates for various organizational needs, ensuring secure communication and authentication. The configuration offers control and flexibility, making it suitable for organizations requiring a customized approach to certificate management.

<br>

## Future Steps

The next phase involves generating certificate requests and issuing certificates from this CA, which will be covered in another demo. This process will further extend the capabilities of the private CA in managing the certificate lifecycle within the organization.
