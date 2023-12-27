# Managing Extended ACL Linux File System Permissions

<br>

## Overview

Extended Access Control Lists (ACLs) in Linux provide a way to assign more granular permissions for files and directories than the standard user, group, and other permissions allow.

<br>

## Preparing for ACL Management

1. **Check for ACL Support**: Not all Linux distributions include ACL support by default.
2. **Install ACL Package**: On Ubuntu Server, install the ACL package using `sudo apt install acl`.

<br>

## Using `getfacl` Command

- **Purpose**: The `getfacl` command is used to display the ACLs of a file or directory.
- **Usage Example**: To view the ACL of `budget1.txt`, use `getfacl budget1.txt`. It will show the permissions for the owner (`lbrenner`), the group (`eastadmins`), and any other specified users or groups.

<br>

## Using `setfacl` Command

- **Purpose**: The `setfacl` command is used to modify the ACLs of a file or directory.
- **Modifying User Permissions**:
  - Example: `sudo setfacl -m u:mbishop:rw budget1.txt` will grant the user `mbishop` read and write permissions on `budget1.txt`.
- **Modifying Group Permissions**:
  - Example: `sudo setfacl -m g:westadmins:r budget1.txt` will grant the group `westadmins` read permission on `budget1.txt`.

<br>

## Practical Example

1. **Navigating to Directory**: Change to the directory containing the file, e.g., `cd budgets`.
2. **Viewing Current Permissions**: Use `ll` to list the current permissions of `budget1.txt`.
3. **Applying ACLs**:
   - Use `setfacl` to assign specific permissions to additional users or groups.
   - Note: A plus sign (`+`) next to the permissions in the `ll` output indicates that extended ACLs are set on the file.

<br>

## Summary

- **Extended ACLs**: Offer the flexibility to set detailed permissions for additional users and groups beyond the basic POSIX permissions.
- **Managing ACLs**: Requires the use of `getfacl` and `setfacl` commands for viewing and setting permissions, respectively.
- **Use Cases**: Ideal for scenarios where complex permission settings are required, which cannot be fulfilled by standard Linux permissions alone.
