# Configuring Sudo in Linux

<br>

## Introduction

This guide explains how to configure `sudo` in Linux, enabling regular users to execute privileged commands.

<br>

### Understanding Sudo

- **Purpose**: `sudo` allows users to run commands that typically require elevated privileges.
- **Example**: Without `sudo`, certain commands like `fdisk -l` may result in permission denials.

<br>

### Editing the Sudoers File

- **Access**: Use `sudo visudo` to safely edit the sudoers file.
- **File Location**: `/etc/sudoers`
- **Temporary File**: Modifications are made in `/etc/sudoers.tmp` to prevent syntax errors.

<br>

### Syntax of the Sudoers File

- **User Privileges**:
  - **Format**: `username ALL=(ALL:ALL) ALL`
  - **Explanation**:
    - **First 'ALL'**: Specifies the hosts from which the user can run the commands.
    - **'(ALL:ALL)'**: The run-as user and group for executing commands.
    - **Last 'ALL'**: Defines the commands the user is allowed to run.

<br>

### Configuring Specific Command Execution

- **Example**: Allow user `jgold` to run `fdisk`.
- **Syntax**: `jgold ALL=(ALL) /usr/sbin/fdisk`
- **Verification**: After saving changes in `visudo`, check `/etc/sudoers` to confirm the addition.

<br>

### Testing the Configuration

- **Switch to User**: `su - jgold`
- **Test Commands**:
  - Without `sudo`: `fdisk -l` results in permission denial.
  - With `sudo`: `sudo fdisk -l` executes successfully.

<br>

### Important Points

- **Safety**: Always use `visudo` to edit the sudoers file to avoid syntax errors.
- **Locating Binaries**: Use `whereis [command]` to find the path of binaries.
- **Testing**: Always test the configuration by switching to the user and trying the command with and without `sudo`.

<br>

## Conclusion

Configuring `sudo` is a crucial aspect of Linux system administration. It enhances security by allowing specific privileges to users without giving them full root access and provides a track record of who executed which commands.
