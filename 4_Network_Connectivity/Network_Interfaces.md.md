# Managing Linux Network Interfaces and IP Addressing

<br>

## Introduction

- **Objective**: Explore key Linux commands for managing network interfaces and IP addressing.

<br>

## Key Networking Commands

1. **ifconfig**:
   - Purpose: Manages network interfaces. Displays network configurations, controls interface states.
   - Usage: `ifconfig`, `sudo ifconfig ens33 up/down`.
   - Details: Shows interface details including IPv4/IPv6 addresses, subnet masks, MAC addresses, and traffic statistics.

2. **ip**:
   - Replacement for `ifconfig`. More versatile for modern Linux distributions.
   - Usage: `ip a` to list all IP information, `ip a add [IP]/[CIDR] dev [interface]` to assign IP addresses temporarily.
   - Note: Changes made with `ip` are not persistent across reboots.

3. **Persistent Network Configuration**:
   - Location: Typically in `/etc/netplan` for Ubuntu Linux.
   - Editing: Use editors like `nano` to modify the network config file (e.g., `00-installer-config.yaml`).
   - Application: Apply changes with `sudo netplan apply` instead of rebooting.

4. **ping**:
   - Purpose: Tests connectivity to a specified IP address using ICMP protocol.
   - Usage: `ping [IP address]`.
   - Note: Continues until stopped (unlike Windows). Useful for basic connectivity checks.

5. **traceroute**:
   - Function: Traces the path packets take to a destination IP.
   - Usage: `traceroute [IP address]`.
   - Consideration: May be blocked by firewalls along the path.

6. **netstat**:
   - Utility: Monitors network connections, listening sockets.
   - Usage: `netstat` for all connections, `netstat | grep ssh` to filter for SSH connections.

<br>

## Demonstrations

- **Network Interface Management**: Using `ifconfig` and `ip` to view and manage network interfaces.
- **Configuring Persistent Settings**: Editing network configuration files for permanent settings.
- **Connectivity Testing**: Employing `ping` and `traceroute` for network path and connectivity checks.
- **Monitoring Connections**: Using `netstat` to observe active network connections.

<br>

## Practical Applications

- **Network Setup**: Configuring and managing network interfaces on Linux systems.
- **Troubleshooting**: Diagnosing connectivity and network issues.
- **Security Monitoring**: Keeping track of network connections and potential unauthorized access.

<br>

## Summary

- **Essential Commands**: Proficiency in commands like `ifconfig`, `ip`, `ping`, and others is crucial for network management in Linux.
- **Dynamic vs Persistent Changes**: Understanding the difference between temporary command line changes and persistent configuration edits.
