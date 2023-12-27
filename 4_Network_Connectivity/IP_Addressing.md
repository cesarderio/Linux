# Understanding IP Addressing in Linux

<br>

## Introduction

- **Objective**: To gain a comprehensive understanding of IPv4 and IPv6 addressing in a Linux environment.
- **Context**: IP addresses are fundamental to network communication, with IPv4 being the longstanding standard and IPv6 emerging as its successor.

<br>

## Key Concepts

1. **IPv4 Addressing**:
   - Description: IPv4 uses 32-bit addresses, divided into four octets (8 bits each), represented in dotted decimal notation (e.g., 192.126.128.190).
   - Notation: Each octet can range from 0 to 255 in decimal values.
   - Reserved Ranges: Addresses like 10.x.x.x, 172.16.x.x - 172.31.x.x, and 192.168.x.x are reserved for internal use and are not routed over the internet.

2. **Subnet Masks in IPv4**:
   - Purpose: Defines which part of the IP address identifies the network and which part identifies a host.
   - Representation: Can be in decimal notation (e.g., 255.255.255.0) or CIDR notation (e.g., /24).

3. **IPv6 Addressing**:
   - Description: IPv6 uses 128-bit addresses, a significant increase from IPv4, allowing a larger number of unique addresses.
   - Notation: Uses hexadecimal representation (e.g., fe80::20c:29ff) and separates sections with colons.
   - Network Mask: Typically represented in CIDR format (e.g., /64).

<br>

## Demonstrations

1. **Working with IPv4 Addresses**:
   - Understanding and configuring IPv4 settings on Linux systems.
   - Recognizing the significance of different octet ranges and subnet masks.

2. **Transitioning to IPv6**:
   - Grasping the expanded addressing capabilities of IPv6.
   - Adapting to the hexadecimal representation and longer address format.

<br>

## Practical Applications

- **Network Configuration**: Essential for setting up and managing network interfaces on Linux systems.
- **Troubleshooting**: Key for diagnosing and resolving network connectivity issues.
- **Future-Proofing**: Understanding IPv6 is increasingly important as the world transitions from IPv4 due to address exhaustion.

<br>

## Summary

- **Understanding IP Addressing**: Mastery of both IPv4 and IPv6 is crucial for Linux technicians in today's networking environment.
- **Key Differences**: Recognizing the distinct characteristics and applications of IPv4 and IPv6 addresses in various networking scenarios.
