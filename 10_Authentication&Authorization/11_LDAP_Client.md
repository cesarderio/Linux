# Installing and Configuring an LDAP Client on Ubuntu

<br>

## Introduction

This demonstration guides you through the process of setting up an LDAP client on Ubuntu, allowing it to authenticate users against a centralized LDAP server.

<br>

### Preparation and Verification

1. **Ensure Connectivity**:
   - Verify that the client can connect to the LDAP server (e.g., using `ping`).
   - Check the LDAP server status with `sudo service slapd status`.
   - Use `sudo slapcat` to view the LDAP directory and confirm user and group entries.

2. **User and Group Definitions**:
   - Examine LDAP directory entries (like `ldapuser1` and `salesgroup`) and their corresponding Linux attributes.

<br>

### LDAP Client Installation

1. **Install Necessary Packages**:
   - Install `libnss-ldapd`, `libpam-ldapd`, and `ldap-utils` with `sudo apt install libnss-ldapd libpam-ldapd ldap-utils -y`.

2. **Configuration Prompts**:
   - Enter the LDAP server URI (e.g., `ldap://ubuntu1`) and the LDAP search base (e.g., `dc=quick24x7,dc=local`).

3. **Configure Services for LDAP**:
   - Ensure `passwd`, `group`, and `shadow` services use LDAP.

<br>

### Additional Configuration

1. **Edit PAM Configuration**:
   - Modify `/etc/pam.d/common-session` to include `session optional pam_mkhomedir.so skel=/etc/skel umask=077`.
   - This line creates home directories for LDAP users based on `/etc/skel`.

2. **Restart Client Daemons**:
   - Restart `nscd` and `nslcd` daemons for the changes to take effect.

<br>

### Testing LDAP Client

1. **Verify No Local Account**:
   - Check `/etc/passwd` for the absence of the LDAP user (e.g., `ldapuser1`).

2. **Switch to LDAP User**:
   - Use `su - ldapuser1` to switch to the LDAP user.
   - The prompt for a password confirms that the user is recognized via LDAP.

3. **Validate Successful Login**:
   - Upon successful login, verify the creation of the user's home directory and the user's active session.

<br>

## Conclusion

Configuring an LDAP client involves installing necessary packages, setting up configuration files, and ensuring seamless integration with the LDAP server. This setup enables centralized user management and authentication across multiple Linux hosts.
