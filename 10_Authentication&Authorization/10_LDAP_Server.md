# Installing and Configuring an LDAP Server on Ubuntu

<br>

## Introduction

This demonstration covers setting up and configuring an LDAP (Lightweight Directory Access Protocol) server on an Ubuntu machine, essential for centralized network directory management.

<br>

### Initial Setup

1. **Setting Hostname**:
   - Use `sudo hostnamectl set-hostname ubuntu1` to set the hostname correctly.

2. **Editing Hosts File**:
   - Modify `/etc/hosts` to include the server's IP address and hostname.

3. **Installing LDAP Components**:
   - Install `slapd` and `ldap-utils` packages using `sudo apt install slapd ldap-utils`.
   - Set up an administrator password during installation.

4. **Verifying Installation**:
   - Use `sudo slapcat` to check LDAP information.
   - Check LDAP server status with `sudo service slapd status`.

<br>

### LDAP Configuration

1. **Reconfiguring slapd**:
   - Run `sudo dpkg-reconfigure slapd` and follow the prompts.
   - Set DNS domain name (e.g., `quick24x7.local`).
   - Set the organization name and confirm the administrator password.
   - Choose not to remove the database when `slapd` is purged.
   - Move the old database if prompted.

2. **Updating LDAP Configuration File**:
   - Edit `/etc/ldap/ldap.conf`.
   - Set BASE to `dc=quick24x7,dc=local` and URI to `ldap://ubuntu1:389`.

3. **Testing Server Response**:
   - Execute `sudo ldapsearch -x` to ensure the server responds to queries.

<br>

### Adding Entries to LDAP Directory

1. **Creating LDIF File**:
   - Create an LDIF file (`ou.ldif`) for adding entries like organizational units or user accounts.

2. **LDIF File Content**:
   - Include details like distinguished name (`dn: ou=hq,dc=quick24x7,dc=local`) and object classes.

3. **Adding Entry to LDAP**:
   - Use `sudo ldapadd -x -D "cn=admin,dc=quick24x7,dc=local" -W -f ou.ldif` to add the entry.
   - Authenticate with the LDAP admin password.

4. **Verifying Addition**:
   - Confirm the new entry using `sudo slapcat` or `sudo ldapsearch -x`.

<br>

## Conclusion

This LDAP server setup on Ubuntu demonstrates the creation of a centralized network directory for user management. It shows the installation, configuration, and addition of entries to the LDAP directory, preparing the server for network-wide user authentication and management.
