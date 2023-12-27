# Dynamic Host Configuration Protocol (DHCP) in Linux

<br>

## Overview

- **DHCP**: Automates the assignment of IP addresses, subnet masks, gateway, and other IP parameters.
- **Benefit**: Simplifies network management by reducing the need for manual IP configuration.

<br>

## DHCP Process

1. **Discovery**: Client sends a broadcast to find DHCP servers on the local network.
2. **Offer**: DHCP server responds with an IP configuration offer.
3. **Request**: Client accepts the offer.
4. **Acknowledgment**: Server acknowledges and the client can communicate on the network.

<br>

## Configuring DHCP on Ubuntu Desktop

- **IPv4 Settings**: Set to 'Automatic (DHCP)' for dynamic IP configuration.
- **Advanced Configuration**: `/etc/netplan` files can be edited for DHCP settings.

<br>

## DHCP Server Configuration

- **Package Selection**: Choose a suitable DHCP server package (e.g., `kea`).
- **Configuration File**: Edit `/etc/kea/kea-dhcp4.conf`.
  - Define interfaces for DHCP (e.g., `"interfaces": ["eth1"]`).
  - Set subnet information and IP address pool.
- **Additional Settings**: Lease duration, DNS servers, default gateway, etc.

<br>

## Security Considerations

- **Pros and Cons**: Easier to connect but lacks authentication; potential security risk.
- **Risk of Compromise**: If compromised, DHCP server can disrupt network connectivity.
- **Manual Configuration**: More secure but less convenient, especially for dynamic networks.
- **Denial-of-Service (DoS) Potential**: A compromised DHCP server can lead to network connectivity issues.

<br>

## Summary

DHCP is crucial for efficient network management, offering automated IP configuration. However, it requires careful consideration regarding security, especially in sensitive environments. Configuring DHCP on Linux involves selecting an appropriate server package and editing configuration files, while also considering potential security risks.
