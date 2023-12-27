# Installing and Configuring Apache Web Server on Ubuntu Linux

<br>

## Introduction

Setting up an Apache Web Server on Ubuntu Linux involves several steps including installation, configuration, and ensuring firewall settings permit web traffic. This process is crucial for hosting websites, whether for public web apps, internal applications, or development environments.

<br>

## Installation Steps

1. **Update Package Repositories**:
   - Command: `sudo apt update`
   - Ensures the server has the latest list of packages.

2. **Install Apache2**:
   - Command: `sudo apt install apache2`
   - Installs the Apache2 web server package.

3. **Check Apache2 Status**:
   - Command: `sudo service apache2 status`
   - Initially, Apache2 is inactive.

4. **Start Apache2 Service**:
   - Command: `sudo service apache2 start`
   - Activates the Apache web server.

<br>

## Configuring Firewall Settings

1. **Allow HTTP Traffic**:
   - Command: `sudo ufw allow 80/tcp`
   - Permits traffic on HTTP port 80.

2. **Optional: Allow HTTPS Traffic**:
   - Command: `sudo ufw allow 443/tcp`
   - Needed if HTTPS with SSL/TLS is configured.

<br>

## Exploring Apache2 Configuration Files

1. **Apache2 Main Configuration File**:
   - Location: `/etc/apache2/apache2.conf`
   - Contains global settings and references to other configuration files.

2. **Ports Configuration**:
   - File: `ports.conf`
   - Specifies listening ports (80 for HTTP, 443 for HTTPS if SSL is enabled).

3. **Web Server Directory**:
   - Default Location: `/var/www/html`
   - Contains the web files served by Apache.

4. **Apache2 Logs**:
   - Location: `/var/log/apache2/`
   - Stores Apache web server logs.

<br>

## Testing the Web Server

1. **Accessing the Default Web Page**:
   - Use a web browser to navigate to the server's IP address (e.g., `http://192.168.2.156`).
   - The Apache2 Ubuntu Default Page should display, confirming the server is operational.

<br>

## Additional Steps

- **Secure the Connection**: Implement HTTPS by configuring SSL/TLS and obtaining a PKI certificate.
- **Web Development**: Developers can now build and deploy web applications, placing files in the appropriate web server directory (`/var/www/html`).

<br>

## Conclusion

The installation and initial configuration of Apache Web Server on Ubuntu Linux are straightforward. Ensuring the server is accessible through the firewall and testing with the default web page are crucial final steps. Further configurations for security, virtual hosts, and custom applications will depend on specific needs.
