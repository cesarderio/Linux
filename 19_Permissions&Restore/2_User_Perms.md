# Troubleshooting User and File Permissions in Linux

<br>

## **User Account Management**

1. **Creating and Managing User Accounts**:
   - **Creating a User**: `sudo useradd [username]`.
   - **Setting a Password**: `sudo passwd [username]`.
   - **Locking a User Account**: `sudo passwd -l [username]`.
   - **Unlocking a User Account**: `sudo passwd -u [username]`.
   - **Verifying in `/etc/shadow`**: Locked accounts show an exclamation mark before the password hash.

<br>

### **Access Control Configuration**

1. **Using `/etc/security/access.conf`**:
   - Controls user/group access for login.
   - Denies or allows specific users/groups to log into the system.
   - Can block access to local text-based terminals and network logins.

<br>

### **Handling the No Login File**

1. **Using `/etc/nologin`**:
   - Disables logins for all users except root.
   - Useful for maintenance periods.

<br>

### **File Permissions Management**

1. **Checking File Permissions**:
   - Use `ll` for a detailed listing of permissions and ownership.
   - Syntax: `ll [directory/file]`.

2. **Changing File Ownership and Permissions**:
   - `sudo chmod [options] [file/directory]`: Modifies file permissions.
   - `sudo chown [new_owner]:[new_group] [file/directory]`: Changes file ownership.
   - Example: `sudo chmod o+x /budgets` to add execute permissions.

<br>
<br>

### **Troubleshooting File Access Issues**

1. **Permission Denied Errors**:
   - Ensure the correct permissions (read, write, execute) are set.
   - Check ownership (user/group) with `chown` or `chgrp`.

2. **Script Execution Issues**:
   - Require read and execute permissions for scripts and their directories.
   - Adjust with `chmod +x [script]` for execution rights.

<br>

### **Additional Considerations**

- **Root Account Access**: Reset root password using `sudo passwd root` if necessary.
- **User and Group Ownership**: Verify with `ll` and adjust with `chown` or `chgrp`.
- **Service and Daemon Permissions**: Ensure correct permissions for background services.
