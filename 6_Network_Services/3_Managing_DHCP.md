# Managing DHCP Client on Ubuntu Linux

<br>

## Overview

- **Objective**: Understanding the DHCP client configuration and troubleshooting on Ubuntu Linux.
- **Environment**: Both Ubuntu Desktop (with GUI) and Ubuntu Server (CLI-focused).

<br>

## Steps and Commands

<br>

### Ubuntu Desktop

1. **Check Network Manager Service**:
   - Run `sudo service NetworkManager status` to ensure it is active.
   - Examine the log for any error messages or warnings.

2. **View DHCP Transactions**:
   - Use `sudo cat /var/log/syslog | grep DHCP` to inspect DHCP logs.
   - Look for new lease information and any error messages.

3. **Check IP Configuration**:
   - Run `ip a` to view the current IP address and confirm DHCP assignment.

4. **GUI Method**:
   - Open network settings and check IPv4 settings for `Automatic (DHCP)`.
   - Optional DNS configuration.

5. **Name Resolution Test**:
   - Use `sudo nslookup` to test DNS resolution.
   - Verify that domain names resolve correctly to IP addresses.

<br>

### Ubuntu Server

1. **Network Manager Absence**:
   - `NetworkManager` service might not be found in Ubuntu Server.
   - Server configurations may differ from the desktop version.

2. **Netplan Configuration**:
   - Navigate to `/etc/netplan` and view configuration files.
   - Check `dhcp4` settings in the YAML file.

3. **Manual DHCP Actions**:
   - Use `sudo dhclient` to manually initiate a DHCP request.
   - For renewal, use `sudo dhclient -r <interface>`.

<br>

## Summary

- DHCP client setup and troubleshooting on Ubuntu Linux involves using command-line tools and, for the desktop version, GUI settings.
- Regularly checking DHCP logs, network settings, and IP configurations is key to ensuring a functional network setup.
- Differences between desktop and server editions in handling network configurations are notable, with desktops using NetworkManager and servers relying on Netplan.
