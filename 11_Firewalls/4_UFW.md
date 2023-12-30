# Configuring Uncomplicated Firewall (UFW) in Linux

<br>

## Introduction

This guide covers setting up and managing the Uncomplicated Firewall (UFW) in Linux, a user-friendly interface for iptables, which has become increasingly popular in many Linux distributions.

<br>

### Basic UFW Commands and Configuration

1. **Checking UFW Status**:
   - Use `sudo ufw status` to check if UFW is active or inactive.

2. **Enabling UFW**:
   - Activate UFW with `sudo ufw enable`. This may disrupt existing SSH connections.

3. **Listing Applications**:
   - After enabling UFW, check available applications with `sudo ufw app list`.

4. **Verbose Status**:
   - Use `sudo ufw status verbose` for detailed information on UFW settings and rules.

<br>

### Adding Rules in UFW

1. **Allowing Specific Applications**:
   - Allow an application (e.g., Apache) using `sudo ufw allow Apache`.
   - Install the application (e.g., `sudo apt install apache2`) to add it to UFW’s recognized applications.

2. **Allowing by Port Number**:
   - For custom rules, specify the port number directly, e.g., `sudo ufw allow 389` for LDAP on port 389.

3. **Adding Protocol-Specific Rules**:
   - Specify the protocol with the port, like `sudo ufw allow 514/udp` for UDP traffic on port 514.

4. **Listing Rules with Numbers**:
   - Use `sudo ufw status numbered` to view rules with line numbers, helpful for management.

<br>

### Managing and Deleting Rules

1. **Deleting Rules by Number**:
   - Remove rules by number, e.g., `sudo ufw delete 6`.

2. **Specifying IP Ranges**:
   - Allow or deny traffic from specific IP ranges, e.g., `sudo ufw allow from 199.126.34.0/24`.

<br>

## Conclusion

UFW provides a simplified approach to firewall management in Linux, suitable for both beginners and experienced users. It offers a balance of functionality and ease of use, making it a favorable choice for many Linux distributions.
