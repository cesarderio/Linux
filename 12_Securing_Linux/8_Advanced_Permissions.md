# Managing Advanced File System Permissions in Linux

<br>

## Overview of Special Permission Bits

In Linux, advanced file system permissions like the sticky bit, user ID bit (SUID), and group ID bit (SGID) provide additional control over file access and execution.

<br>

### The Sticky Bit

- **Purpose**: Ensures only file owners can delete their files in a shared directory.
- **Example**: Creating a shared directory and setting the sticky bit.

  ```bash
  sudo mkdir /shared_files
  sudo chmod +t /shared_files  # Setting the sticky bit
  ```

  [Video description begins] Command execution in Linux terminal to create a directory and set the sticky bit. [Video description ends]

<br>

### The User ID Bit (SUID)

- **Purpose**: Allows a file to be executed with the permissions of the file's owner.
- **Setting SUID**:

  ```bash
  sudo touch /shared_files/script1.sh
  sudo chmod u+s /shared_files/script1.sh  # Setting SUID bit
  ```

  [Video description begins] Command execution in Linux terminal to create a script and set the SUID bit. [Video description ends]

- **Effect of SUID**: The script runs with the permissions of the owning user, regardless of who executes it.

<br>

### The Group ID Bit (SGID)

- **Purpose**: Similar to SUID, but the file executes with the permissions of the owning group.
- **Setting SGID**:

  ```bash
  sudo chgrp eastadmins /shared_files/script1.sh
  sudo chmod g+s /shared_files/script1.sh  # Setting SGID bit
  ```

  [Video description begins] Command execution in Linux terminal to change the group of a script and set the SGID bit. [Video description ends]

<br>

### Numeric Values of Special Bits

- **SUID Bit**: 4
- **SGID Bit**: 2
- **Sticky Bit**: 1

These values are significant when using octal (numeric) representation of permissions.

<br>

### Practical Usage

- **Removing Execute Permission**:

  ```bash
  sudo chmod o-x /shared_files  # Removing execute permission
  ```

  [Video description begins] Command execution in Linux terminal to remove execute permission from the shared directory. [Video description ends]

- **Understanding Numeric Permissions**: For example, `chmod 1660` on a file sets the sticky bit (1), read-write (6) for owner and group, and no permissions (0) for others.

<br>

### Conclusion

Understanding and correctly implementing advanced file system permissions like the sticky bit, SUID, and SGID is crucial for securing shared resources on Linux systems. These special bits provide fine-grained control over file and directory permissions, enhancing overall system security.
