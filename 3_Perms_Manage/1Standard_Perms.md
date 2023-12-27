# Permissions Management

<br>

## Linux File System Security Commands

<br>

### Overview

- **Purpose**: Linux file system security commands are used to control access to files and directories, adhering to security principles like the principle of least privilege.
- **Commands**:
  - `chmod` (Change Mode): Modify file and directory permissions.
  - `chgrp` (Change Group): Change the group ownership of a file or directory.
  - `chown` (Change Owner): Change the user and/or group ownership of a file or directory.

<br>

### Understanding File Permissions

- **Permissions**:
  - Read (r): Numeric value of 4.
  - Write (w): Numeric value of 2.
  - Execute (x): Numeric value of 1.
- **Permission Sets**: For the owning user, owning group, and others.
- **Numeric Representation**: Sum of permission values (e.g., rwx = 7, rw- = 6).

<br>

### Using `chmod`

- **Numeric Method**: `chmod [permissions] [file/directory]`
  - Example: `chmod 740 file1.txt` sets read, write, execute for owner, read for group, and none for others.
- **Symbolic Method**: `chmod [u/g/o/a]=[permissions] [file/directory]`
  - Example: `chmod u=rwx,g=r file1.txt` gives the owner rwx permissions, and the group r permission.
- **Recursive Change**: `-R` flag to apply permissions to a directory and all its contents.
  - Example: `chmod 755 /budgets -R`

<br>

### Using `chgrp` and `chown`

- **Change Group (`chgrp`)**: Change the group ownership of a file or directory.
  - Example: `chgrp newgroup file.txt` changes the group of `file.txt` to `newgroup`.
- **Change Owner (`chown`)**: Change the user and/or group ownership.
  - Example: `chown newuser file.txt` changes the owner of `file.txt` to `newuser`.
  - Change both user and group: `chown newuser:newgroup file.txt`.

<br>

### Umask

- **Default Permissions**: Controlled by `umask`.
- **Function**: `umask` subtracts permissions from the default set by the system.
- **Example**: A `umask` of 002 results in default file permissions of rw-rw-r--.

<br>

### GUI Tools for Permissions

- File properties in GUI can be used to set permissions (varies across Linux distributions).

<br>

### Summary

- **Linux Filesystem Permissions**: Essential for securing access to files and directories.
- **Commands (`chmod`, `chgrp`, `chown`)**: Provide robust methods for managing permissions and ownership.
- **Permission Management**: Can be performed both via command line and GUI tools.


