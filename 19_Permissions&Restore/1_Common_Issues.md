# Troubleshooting User and File Permissions in Linux

<br>

## **User Account Troubleshooting**

- **Local vs Network Accounts**: Check if the account exists locally in `/etc/passwd` or is network-based (e.g., LDAP, Active Directory).
- **Password Reset**: Use `passwd` command (with `sudo` for non-root accounts) to reset passwords.
- **Account Locking/Unlocking**:
  - **Lock Account**: `sudo usermod -L [username]` (adds an exclamation mark before password hash in `/etc/shadow`).
  - **Unlock Account**: `sudo usermod -U [username]` (removes exclamation mark from `/etc/shadow`).
- **Account Existence**: Verify in `/etc/passwd` or `/etc/shadow`.
- **Network Access**: Ensure network access for authentication if using network-based accounts.

<br>

### **File Permissions Issues**

- **Symptoms**: Inability to delete files, permission denied errors, etc.
- **Sticky Bit**: Check for sticky bit on directories which allows users to delete only their files.
- **Permission Verification**: Use `ll` to check user/group ownership and permissions.
- **Changing Ownership/Group**:
  - **Change Owner**: `chown [user]:[group] [file/directory]`.
  - **Change Group**: `chgrp [group] [file/directory]`.
- **Sudo Privileges**: Ensure users have sudo privileges (added in `/etc/sudoers`).

<br>

### **Script Execution Issues**

- **Read and Execute Permissions**: Required for accessing and running shell scripts.
- **Permission Denial**: Use `chmod +x [script.sh]` to add execute permission.

<br>

### **Access-Control Configurations**

- **/etc/security/access.conf**: Restricts or allows user/group access. Can block login on local terminals or network.
- **Script Execution Example**:
  - **Problem**: `./hello.sh` returns "Permission Denied".
  - **Solution**: `sudo chmod +x hello.sh` followed by running `./hello.sh` successfully.
