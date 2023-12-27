# Configuring HTTPS Binding for Apache Web Server on Ubuntu Linux

<br>

## Overview

This content demonstrates configuring an HTTPS binding for an Apache web server on Ubuntu Linux using a PKI certificate obtained from a private Certificate Authority (CA).

<br>

## Key Steps

1. **Apache Web Server Installation and Verification:**
   - Install Apache 2 with `sudo apt install apache2`.
   - Verify server status using `sudo service apache2 status`.
   - Server’s IP address identified with `ip a`.

2. **Certificate and Key Preparation:**
   - Navigate to the directory containing the certificate (`easy-rsa/pki/issued/`).
   - Review certificate details (`ubuntu1server.crt`), including issuer, validity, and subject.
   - Modify `/etc/hosts` to map the server’s IP address to the DNS name (`www.quick24x7.com`).
   - Create a certificate directory (`/etc/certificate/`) and copy server certificate and private key (`ubuntu1server.key`) there.

3. **Enabling SSL Module on Apache:**
   - Enable SSL module using `sudo a2enmod ssl`.
   - Optionally enable rewrite module (`sudo a2enmod rewrite`).
   - Restart Apache server (`sudo service apache2 restart`).

4. **Configuring Apache for HTTPS:**
   - Edit Apache configuration file (`/etc/apache2/sites-enabled/000-default.conf`).
   - Set VirtualHost to listen on port 443.
   - Enable SSL with `SSLEngine on`.
   - Specify paths for `SSLCertificateFile` and `SSLCertificateKeyFile`.

5. **Apache Configuration Testing:**
   - Check configuration syntax with `sudo apache2ctl configtest`.
   - Restart Apache to apply changes.

6. **CA Certificate Installation on Server:**
   - Copy CA certificate (`ca.crt`) to `/usr/local/share/ca-certificates`.
   - Update CA certificates on the server with `sudo update-ca-certificates`.

7. **Testing HTTPS Connection:**
   - Verify HTTPS connection using `curl` command.
   - If successful, HTML content is returned without certificate trust errors.

<br>

## Conclusion

The demonstration successfully configures an HTTPS binding for an Apache web server on Ubuntu Linux. The process involves installing and verifying the Apache server, preparing the PKI certificate and key, enabling the SSL module, configuring Apache for HTTPS, and ensuring the server trusts the certificate issued by the private CA. This enables secure and encrypted web communication via HTTPS.
