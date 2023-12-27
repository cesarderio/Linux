# Managing Standard Linux File System Permissions

<br>

## Overview

- Managing file system permissions in Linux is crucial for security and adhering to the principle of least privilege.
- Permissions can be managed using GUI tools in desktop environments or command line utilities.

<br>

## File System Permissions

- **Types of Permissions**:
  - Read (r): Numeric value 4.
  - Write (w): Numeric value 2.
  - Execute (x): Numeric value 1.
- **Permission Sets**: Apply to the owning user, owning group, and others.
- **Default Permissions**: Determined by the `umask` value. The default `umask` 0002 results in permissions rw-rw-r-- for new files.

<br>

## Using Command Line Utilities

1. **`chmod` (Change Mode)**:
   - Sets or changes file/directory permissions.
   - Numeric method: `chmod 740 file1.txt` (Read, write, execute for owner; read for group; none for others).
   - Symbolic method: `chmod u=rwx,g=r file1.txt` (Set specific permissions using u=user, g=group, o=others).
   - Recursive change: `chmod -R 755 /budgets` (Apply permissions to a directory and its contents).

2. **`chgrp` (Change Group)**:
   - Changes the group ownership of a file or directory.
   - Example: `chgrp eastadmins budget1.txt` (Change group ownership to `eastadmins`).

3. **`chown` (Change Owner)**:
   - Changes the user and/or group ownership of a file or directory.
   - Change user ownership: `chown lbrenner budget1.txt` (Change owner to `lbrenner`).
   - Change both user and group: `chown lbrenner:eastadmins budget1.txt`.

<br>

## Practical Demonstration

- **Creating Files and Directories**:
  - Use `mkdir` to create directories and `touch` to create files.
  - Example: `mkdir budgets` and `touch budgets/budget1.txt`.

- **Viewing Permissions**:
  - Use `ls -l` to view permissions in long listing format.
  - Permissions are displayed in the leftmost column for user, group, and others.

- **Modifying Permissions**:
  - Adjust permissions with `chmod`, change group ownership with `chgrp`, and change user ownership with `chown`.
  - Add new users and groups using `useradd` and `groupadd`.

<br>

## GUI Tools for Permissions

- In desktop environments, right-click on files or directories and choose "Properties" to modify permissions.

<br>

## Summary

- **File System Permissions**: Essential for controlling access to files and directories in Linux.
- **Commands (`chmod`, `chgrp`, `chown`)**: Provide a comprehensive approach for setting and managing permissions.
- **Flexibility**: Permissions can be managed both through command line and GUI, catering to different user preferences.

