# Deploying a DNS Server on Ubuntu Linux

<br>

## Introduction

- **Objective**: Installing and configuring the BIND9 DNS server on Ubuntu Linux.
- **Overview**: DNS servers are essential for resolving domain names to IP addresses and vice versa.

<br>

## Steps for DNS Server Installation and Configuration

1. **Updating Package Repositories**:
   - Run `sudo apt update` to ensure the package list is current.

2. **Installing BIND9 and Related Packages**:
   - Execute `sudo apt install bind9 bind9utils bind9-doc` for the DNS server, utilities, and documentation.
   - Ensure successful installation and server running status with `sudo service bind9 status`.

3. **Configuring BIND9**:
   - Navigate to `/etc/bind` and examine configuration files like `named.conf`, `named.conf.options`, and `named.conf.local`.
   - Edit `named.conf.options` to set directory paths, enable recursion, and specify DNS forwarders (e.g., Google's 8.8.8.8 DNS server).
   - Set `allow-transfer { none; };` for security, preventing unauthorized zone transfers.

4. **Setting Up Forward Lookup Zone**:
   - In `named.conf.local`, add a zone (e.g., `sales.quick24x7.com`) and specify it as a primary type.
   - Reference the zone file (e.g., `/etc/bind/zones/db.sales.quick24x7.com`).

5. **Creating and Editing Zone File**:
   - Create a new zone file from a template (e.g., `db.local`) and edit it for the specific domain.
   - Set SOA record, A records for domain and subdomains (e.g., `www`), and increment the serial number for updates.
   - Important: Ensure correct syntax and trailing periods in FQDNs within the zone file.

6. **Checking Configuration and Zone File Syntax**:
   - Use `sudo named-checkconf` to verify configuration file syntax.
   - Utilize `sudo named-checkzone` for checking the DNS zone file syntax.

7. **Restarting and Verifying BIND9 Service**:
   - Restart BIND9 with `sudo service bind9 restart`.
   - Confirm the service is active and running with `sudo service bind9 status`.

8. **Allowing DNS Traffic Through Firewall**:
   - If using UFW (Uncomplicated Firewall), run `sudo ufw allow Bind9` to permit DNS traffic.

<br>

## Conclusion

- Successfully installed and configured BIND9 DNS server.
- Ensured security settings to prevent unauthorized access.
- Verified syntax and operational status of the DNS server.
- Prepared for client-side DNS configuration in subsequent demonstrations.

This process establishes a functional DNS server on Ubuntu Linux, capable of resolving domain names for network clients, enhancing network management and connectivity.
