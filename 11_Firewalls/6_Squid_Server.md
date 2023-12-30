# Deploying and Configuring Squid Proxy Server on Ubuntu Linux

<br>

## Introduction

This demonstration covers the installation and basic setup of the Squid proxy server on Ubuntu Linux, a popular open-source proxy solution.

<br>

### Installation and Configuration Steps

1. **Updating Package Repositories**:
   - Start by updating package repositories: `sudo apt update`.

2. **Installing Squid**:
   - Install Squid using: `sudo apt install squid`.

3. **Checking Squid Configuration File**:
   - Examine the Squid configuration: `sudo nano /etc/squid/squid.conf`.
   - Key points to note:
     - Default settings, like `http_access`, control access permissions.
     - Squid listens on port `3128` by default.
     - `acl localnet` can be modified to include internal IP ranges.

4. **Enabling Traffic on Port 3128**:
   - Allow traffic through the firewall for Squid: `sudo ufw allow 'Squid'`.

5. **Verifying Squid Service Status**:
   - Check if the Squid service is active: `sudo service squid status`.

<br>

### Client Configuration for Squid

1. **Setting Up Firefox to Use Squid**:
   - Open Firefox and navigate to the network settings.
   - Configure the proxy setting by entering the IP address of the Squid server and the correct port (3128).

2. **Testing the Proxy Connection**:
   - Initially, input an incorrect port (e.g., 3127) to test the connection failure.
   - Correct the port to `3128` and attempt to access a website like Google.
   - Successful page load confirms the correct setup of Squid.

<br>

### Key Features of Squid

- **Forward Proxy**: Squid acts as a forward proxy, fetching internet content for internal clients.
- **IP Routing**: Unlike other firewall solutions, IP routing is disabled to allow authentication checks.
- **Caching Content**: Squid can cache frequently requested internet content.
- **Configuration Flexibility**: Offers numerous settings for access control, including optional user authentication.

<br>

## Conclusion

Deploying Squid on Ubuntu Linux involves installing the package, configuring access rules, and setting up client devices to use the proxy. Squid offers a robust solution for controlling and monitoring internet access, with capabilities like content caching and authentication.
