# Configuring a Packet Filtering Firewall with iptables in Linux

<br>

## Introduction

This demonstration guides you through setting up a packet filtering firewall using `iptables` on a Linux system. `iptables` is a powerful tool for managing network traffic on Linux, offering control over both incoming and outgoing packets.

<br>

### Configuring Basic iptables Rules

1. **Listing Current Rules**:
   - Run `sudo iptables -L -v -n` to list all current iptables rules with verbose and numeric output.

2. **Allowing ICMP Traffic**:
   - Add a rule to accept ICMP traffic (used by ping): `sudo iptables -A INPUT -i eth0 -p icmp -j ACCEPT`.
   - This rule allows ICMP packets on the `eth0` interface.

3. **Blocking ICMP Traffic**:
   - Add a rule to drop ICMP traffic: `sudo iptables -A INPUT -i eth0 -p icmp -j DROP`.
   - Use `sudo iptables -D INPUT -i eth0 -p icmp -j ACCEPT` to remove the previous accept rule.

4. **Testing ICMP Rule**:
   - From another host, ping the IP address of the Linux host with iptables configured (e.g., `ping 10.0.0.8`).
   - Observe the changes in response based on the iptables rules.

5. **Allowing HTTP Traffic**:
   - Add a rule for HTTP traffic: `sudo iptables -A INPUT -i eth0 -p tcp --dport 80 -j ACCEPT`.
   - This rule allows TCP traffic on port 80 (standard for HTTP) through the `eth0` interface.

<br>

### Key Points

- **Order of Rules**: iptables processes rules in the order they are added. The first rule that matches a packet determines its fate.
- **Deleting Rules**: Use the `-D` option to delete specific rules.
- **Interface Specification**: The `-i` option specifies the network interface (e.g., `eth0`).
- **Protocol and Port**: The `-p` option specifies the protocol (e.g., `tcp`, `icmp`), and `--dport` specifies the destination port.
- **Action**: The `-j` option determines the action (e.g., `ACCEPT`, `DROP`).

<br>

## Conclusion

Configuring iptables involves adding rules to control how different types of network traffic are handled. By specifying criteria such as interface, protocol, and ports, iptables provides granular control over network security on Linux systems.
