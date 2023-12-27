# Configuring DNS Client Settings on Linux Hosts

<br>

## Introduction

- **Objective**: Configure DNS client settings manually on Ubuntu Linux (server edition).
- **Context**: DNS client configuration is essential for resolving domain names to IP addresses.

<br>

## Steps for DNS Client Configuration

1. **Examining `resolv.conf`**:
   - Check `/etc/resolv.conf` which is a symbolic link to `/run/systemd/resolv`.
   - Use `sudo cat /etc/resolv.conf` to view the contents, noting the stub IP address (127.0.0.53).

2. **Modifying Netplan Configuration**:
   - Edit the Netplan YAML configuration file located in `/etc/netplan`.
   - Ensure `dhcp4` is set to `no` for manual configuration.
   - Under `network > ethernets`, specify static IP settings and routes.
   - In the `nameservers` section, list desired DNS server addresses.
   - Apply changes using `sudo netplan apply`.
   - Note: Netplan YAML files require precise indentation and spacing.

3. **Verifying DNS Settings**:
   - `sudo resolvectl status` displays DNS server settings as per Netplan configuration.
   - Test DNS resolution using `ping` and `nslookup` commands to resolve domain names (e.g., `www.google.com`, `www.skillsoft.com`).
   - Use `nslookup` to change DNS server settings temporarily and perform reverse lookups (set type=ptr).

4. **Using DNS Lookup Tools**:
   - Utilize `dig` command for detailed DNS query information (e.g., `dig www.skillsoft.com`).

5. **GUI Tools on Ubuntu Desktop**:
   - Access DNS settings through GUI on Ubuntu Desktop.
   - Modify DNS server entries in network settings (IPv4 tab) even when using DHCP.

<br>

## Conclusion

- Successfully configured DNS client settings on Ubuntu Linux server and desktop versions.
- Manual DNS configuration allows precise control over network settings and resolution.
- Tools like `nslookup` and `dig` are effective for DNS troubleshooting and verification.
- GUI tools provide an alternative method for adjusting DNS settings on desktop environments.

These configurations ensure that Linux clients effectively resolve domain names, enhancing network connectivity and internet access.
