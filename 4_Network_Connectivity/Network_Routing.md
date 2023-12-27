# Understanding Network Routing in Linux

<br>

## Introduction

- **Objective**: Learn about the fundamentals of IP routing and the use of routing commands in Linux.


<br>

## Network Routing Basics

1. **Concept of Routing**:
   - Purpose: Directs network traffic to its destination via the most efficient path, involving one or more routers.
   - Devices: Can be hardware routers or computers with multiple network interfaces and IP routing enabled.

2. **Routing Table**:
   - Function: Each device, including client endpoints, uses an in-memory routing table to determine the path for network packets.
   - Default Route: IPv4 notates this as 0.0.0.0, directing traffic to the default gateway when no specific route is found.

3. **IP Routing and TTL**:
   - TTL (Time to Live): Each packet's TTL decreases by 1 when traversing a router, limiting the maximum route length.

<br>

## Linux Routing Commands

1. **route Command**:
   - Usage: Displays the device's routing table. Can add static route entries.
   - Example: `route` (to display routing table).

2. **Static vs Dynamic Routing**:
   - Static Routing: Manual entry of routing paths. Impractical for large networks.
   - Dynamic Routing: Automated sharing of routes between routers using protocols like RIP, OSPF, and EIGRP.

3. **Adding and Modifying Routes**:
   - Default Gateway: `route add default gw [IP address]`.
   - Specific Host: `route add -host [IP] reject`.
   - Using `ip route`: For example, `ip route add [network]/24 dev eth1`.

4. **traceroute Command**:
   - Function: Traces the path of traffic to a destination.
   - Usage: `traceroute [destination IP or DNS name]`.

5. **Persistent Routing Configuration**:
   - Location: In `/etc/netplan/` for Ubuntu Linux.
   - Method: Modify the config file to add routes with the `routes:` directive.

<br>

## Practical Applications

- **Network Configuration**: Setting up and managing network routing on Linux systems.
- **Troubleshooting**: Diagnosing and solving network path and connectivity issues.
- **Efficiency Optimization**: Ensuring efficient routing of network traffic in a Linux environment.

<br>

## Summary

- **Routing Mastery**: Understanding and managing IP routing is essential for Linux technicians.
- **Command Proficiency**: Familiarity with `route`, `ip route`, and `traceroute` commands for effective network management.
