# Troubleshooting Network Configuration in Linux

<br>

## Using the GUI (Ubuntu Desktop)

- **Accessing Network Settings**: Click the network icon and access settings for detailed network configurations.
- **Wired Network Connection Details**: Review IP addresses, MAC address, default gateway, and DNS servers.
- **IPv4/IPv6 Configuration**: Check and modify settings, including DHCP and manual configurations.

<br>

## Command Line Tools for Troubleshooting

- **IP Command**: `ip a` lists all network interfaces and their configurations.
  - For specific interface details: `ip a show dev [interface_name]`.
- **Changing Interface State**: Use `ip link set [interface_name] up/down` to bring an interface up or down.
- **Editing Netplan Configuration**:
  - Edit with `sudo nano /etc/netplan/[config-file].yaml`.
  - Apply changes with `sudo netplan apply`.
- **Testing DNS Resolution**:
  - `ping www.google.com` for basic connectivity test.
  - `nslookup www.google.com` for DNS name resolution test.
  - `dig www.google.com` for detailed DNS query information.

<br>

## Important Points

- **GUI vs. CLI**: GUI is easier but less common in server environments; CLI provides more detailed control and is universally applicable.
- **Netplan Configuration**: YAML-based configuration in recent Ubuntu versions requires precise syntax.
- **DNS Tools**: `nslookup` and `dig` offer different levels of detail for DNS troubleshooting.
