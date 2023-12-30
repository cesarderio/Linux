# Pluggable Authentication Modules (PAM) in Linux

<br>

## Introduction

This section explores the concept of Pluggable Authentication Modules (PAM) in Linux, a key subsystem in managing security services.

<br>

## What is PAM?

- **Definition**: PAM is a built-in subsystem in all Linux distributions.
- **Function**: It separates authentication tasks from applications, acting as an intermediary between security-needing apps and underlying security mechanisms.

<br>

## Uses of PAM

- **Account Verification and Authentication**: Facilitates user login processes.
- **Password Management**: Assists in updating user passwords.
- **Security Tasks**: Includes auditing and other security-related functions.

<br>

## PAM Configuration

- **Typical Usage**: Rarely configured directly by Linux technicians.
- **Exceptions**: Certain scenarios like LDAP client software installation require PAM configuration modifications.

<br>

## Exploring PAM Library Files

- **Location**: `/lib/security`.
- **File Extension**: PAM modules typically have the `.so` extension.
- **Examples**: `pam_nologin.so` (restricts logins), `pam_ftp.so`.

<br>

### PAM Configuration Files

- **Location**: `/etc/pam.d`.
- **Example**: `common-account` file for LDAP client configuration.
- **Other Services**: Includes `cron`, `login`, `passwd`, `sudo`.

<br>

### Syntax in PAM Configuration Files

- **Columns**:
  1. **Module Type** (e.g., account).
  2. **Control Flag** (e.g., required).
  3. **Module Name** (e.g., `pam_nologin.so`).
  4. **Additional Module Arguments**.

- **Example**: An `account required pam_nologin.so` line means all listed modules must succeed.

<br>

### Viewing Binary Command Shared Objects

- **Command**: `sudo ldd /bin/su`.
- **Purpose**: Shows shared objects referenced by commands like `su`.
- **Example**: References to `libpam.so.0`, `libpam_misc.so.0`.

<br>

### Practical Example: SSH Denied Users

- **Configuration File**: `/etc/pam.d/sshd`.
- **Syntax**: `auth required pam_listfile.so onerr=succeed`.
- **Purpose**: Block SSH login for specified users in a designated file (e.g., `/etc/ssh/deniedusers`).

<br>

### Implementing SSH User Block

- **Example**: Creating a `deniedusers` file with a username `mbishop`.
- **Outcome**: User `mbishop` is denied SSH access despite correct credentials.

<br>

## Conclusion

PAM in Linux is a sophisticated and essential subsystem for managing authentication and security tasks. Understanding and configuring PAM, though infrequent, is crucial for maintaining a secure Linux environment.
