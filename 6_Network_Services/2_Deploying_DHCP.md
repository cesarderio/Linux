# Installing and Configuring a DHCP Server on Ubuntu Linux

<br>

## Overview

- **Purpose**: To centrally manage IP configurations for network clients.
- **Tool**: Kea DHCP server stack for IPv4 (and IPv6).

<br>

## Installation Steps

1. **Install Kea DHCP Server**:
   - Command: `sudo apt install kea`
   - Confirm the installation by typing `y` and pressing `Enter`.

2. **Configure Kea DHCP Server**:
   - Navigate to the configuration directory: `/etc/kea`.
   - Edit the configuration file: `sudo nano kea-dhcp4.conf`.
   - The file contains settings for:
     - Subnet information.
     - IP address pools for DHCP clients.
     - Default gateway/router IP address.
     - DNS server addresses.

3. **Reservations (Optional)**:
   - For assigning consistent IPs to devices with specific MAC addresses (e.g., printers, servers).
   - Add reservations in the configuration file.

4. **Activate and Verify DHCP Server**:
   - Start the server: `sudo service kea-dhcp4-server start`.
   - Check the status: `sudo service kea-dhcp4-server status`.
   - Verify it’s active and running.

5. **Logging and Troubleshooting**:
   - View logs and troubleshoot using:
     - `sudo journalctl -u kea-dhcp4-server`
     - `sudo cat /var/log/syslog | grep -i kea`

<br>

## Summary

- The Kea DHCP server is installed and configured on Ubuntu Linux to manage network IP configurations centrally.
- Key configurations involve setting up subnet information, IP pools, and defining network gateways and DNS servers.
- The server's status and logs are crucial for ensuring proper operation and troubleshooting any issues.
