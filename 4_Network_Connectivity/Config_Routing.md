# Configuring Linux Routing Using the Route Command

<br>

## Introduction

- **Objective**: Understand how to configure network routing in Linux using the `route` and `ip` commands.
- **Host**: Dan Lachance guides through the process of routing configuration in the Linux OS.

<br>

## Configuring Routing in Linux

1. **Viewing the Routing Table**:
   - Commands: `route` or `ip route show` to display the current routing table.
   - Details: Shows default routes, device information, and metric values.

2. **Adding a Route**:
   - Command: `sudo ip route add [network]/[mask] via [gateway IP] dev [interface]`.
   - Purpose: Directs traffic destined for a specific network through a specified gateway.
   - Example: Routing traffic for the 200.1.1.0/24 network via 192.168.2.90 on `ens33`.

3. **Deleting a Route**:
   - Command: `sudo ip route delete [network]/[mask]`.
   - Use: Removes a specific routing entry from the table.

4. **Making Routes Persistent**:
   - Location: `/etc/netplan` directory in Ubuntu Linux.
   - Editing: Modify the netplan configuration file using a text editor like `nano`.
   - Syntax: Adding routes using the `routes:` section, ensuring correct YAML formatting.

5. **Applying Changes**:
   - Command: `sudo netplan apply` to enact changes in the configuration file.
   - Verification: Running `ip route show` to see the updated routing table.

<br>

## Practical Applications

- **Network Configuration**: Customizing routing for specific network requirements.
- **Troubleshooting**: Identifying and correcting routing issues for network connectivity.
- **Persistence**: Ensuring routing configurations remain effective after system restarts.

<br>

## Summary

- **Command Proficiency**: Mastery of `route` and `ip route` commands is vital for Linux network management.
- **Configuration Persistence**: Understanding how to make routing changes permanent with netplan configuration.
