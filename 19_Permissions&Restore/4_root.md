# Resetting a Forgotten Root Password in Linux

<br>

## **Context**

- **Root Account**: Super admin account with ultimate privileges.
- **Necessity**: Sometimes required to sign in as root despite alternatives like sudo.

<br>

### **Initial Checks**

- **Current User Verification**: Use `whoami` to check logged-in user.
- **Sudoers File Inspection**:
  - Accessed with `sudo nano /etc/sudoers`.
  - Checks for users with sudo privileges (`%admin`, `%sudo`).

<br>

### **Using Sudo to Reset Password**

- **Example**: `sudo passwd root` to reset root password if user has sudo privileges.
- **User Group Verification**: Use `sudo cat /etc/group | grep sudo` to check group membership.

<br>

### **Using Installation Media for Password Reset**

- **Accessing Recovery Mode**:
  - Boot from installation media.
  - Use GRUB menu to enter recovery mode.
  - Select option to drop to a root shell prompt.

<br>

### **Setting Password in Recovery Mode**

- **Verifying Root Access**: Use `whoami` in the recovery shell.
- **Ensuring Read/Write Mode**:
  - Check if `/dev/sdc1` (root filesystem) is mounted in read-write mode.
  - If not, use `mount -o remount /`.

<br>

### **Resetting Password**

- **Command**: `passwd` to set and confirm the new password.
- **Outcome**: Root password reset to a known value.

<br>

## **Alternate Methods**

- **Physical or Virtual Access**: Required for recovery mode access.
- **Using Snapshots or Backups**: Restore to a point where the root password is known.

<br>

### **Resetting Password in Cloud Environments (e.g., Microsoft Azure)**

- **Access VM Properties**: In Azure, select the Linux VM.
- **Reset Options**:
  - Under 'Help', find 'Reset password'.
  - Specify username and new password for password-based authentication.
  - Reset SSH public key for SSH authentication.

<br>

## Key Takeaways

- **Root Password Recovery**: Essential for situations where sudo is not an option or the root password is forgotten.
- **Sudoers File**: Critical for understanding which users have sudo privileges and can reset the root password.
- **Recovery Mode**: A reliable method for resetting the root password directly, requiring physical or virtual access to the system.
- **Cloud Environments**: Offer built-in tools for resetting credentials, accommodating both password and SSH key-based authentication methods.
