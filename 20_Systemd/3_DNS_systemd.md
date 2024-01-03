# Troubleshooting DNS Issues in Linux

<br>

## Overview

- **DNS Role**: Essential for resolving domain names to IP addresses.
- **Common Scenario**: Users typically enter domain names, not IP addresses.

<br>

### Initial Checks

1. **Verify Network Interface**
   - Command: `ip a`
   - Check: Network interface status and valid IP addresses.

2. **Check Default Route**
   - Command: `ip route`
   - Verify: Default route configuration for network access.

<br>

### DNS Troubleshooting Tools

1. **nslookup**
   - Usage: Query DNS records, e.g., `nslookup www.skillsoft.com`.
   - Outcome: Provides non-authoritative answers from DNS servers.
   - Confirmation: Ensures DNS resolution is functioning.

2. **systemd-resolved Configuration**
   - File: `/etc/systemd/resolved.conf`
   - Editing: Use `sudo nano` to add DNS server IP addresses.
   - Application: Restart systemd-resolved service to apply changes.
   - Command: `sudo systemctl restart systemd-resolved.service`

3. **resolv.conf Considerations**
   - File: `/etc/resolv.conf`
   - Note: Managed by systemd-resolved in modern Linux; manual edits discouraged.
   - Legacy: Older systems might require manual DNS configurations in this file.

4. **resolvectl**
   - Usage: Alternative DNS query tool, e.g., `sudo resolvectl query skillsoft.com`.
   - Benefit: Offers different insights compared to nslookup or dig.

5. **Flushing DNS Cache**
   - Command: `sudo resolvectl flush-caches`
   - Purpose: Clear cached DNS queries to ensure accurate testing.
   - Scenario: Useful when correcting previous DNS configuration errors.

<br>

## Conclusion

Understanding and effectively using DNS troubleshooting tools like `nslookup`, `systemd-resolved`, and `resolvectl` is crucial for resolving DNS issues in Linux. Regular checks of network interfaces, default routes, and DNS configurations help maintain consistent network connectivity. Being aware of the role of systemd in modern Linux distributions for DNS management is essential for any Linux technician.
