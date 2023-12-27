# Extended ACL File System Permissions

<br>

## Introduction to ACLs

- **Purpose**: ACLs provide more granular control over file and directory permissions beyond the standard Linux permissions (owner, group, others).
- **Flexibility**: Allows setting permissions for multiple individual users and groups on the same files and directories.

<br>

## Setting Up ACLs

1. **Installation**:
   - ACL tools may not be included by default in all Linux distributions.
   - Install the ACL package: `sudo apt install acl`.

2. **Key Commands**:
   - `setfacl`: Set or modify ACL permissions.
   - `getfacl`: Retrieve or display ACL permissions.

<br>

## Using ACL Commands

1. **Viewing ACLs** (`getfacl`):
   - Example: `getfacl file1.txt` shows ACLs for `file1.txt`, including permissions for specified users and groups.

2. **Modifying ACLs** (`setfacl`):
   - Adding User Permissions: `setfacl -m u:mbishop:rwx file1.txt` (Adds read, write, execute permissions for user `mbishop` on `file1.txt`).
   - Adding Group Permissions: `setfacl -m g:eastadmins:rw file1.txt` (Adds read and write permissions for group `eastadmins`).
   - Recursive Permission Setting: `setfacl -R -m o:r /dir1` (Sets read permission for others on `dir1` and its contents).

3. **Backing Up and Restoring ACLs**:
   - Backing Up: `getfacl -R /dir1 > aclpermissionsbackup.txt` (Saves ACLs of `dir1` to a file).
   - Restoring: `setfacl --restore=aclpermissionsbackup.txt` (Restores ACLs from the backup file).

<br>

## Understanding ACL Entries

- **Mask**: Acts as a filter that sets the maximum allowed permissions, overriding any assigned permissions.

<br>

## Example Scenario

- In the example, `budget1.txt` has a standard permission set, indicated by a `+` sign, showing that an ACL has been applied.
- `getfacl budget1.txt` reveals:
  - User `lbrenner` as the owner with specific permissions.
  - Additional user `mbishop` with distinct permissions.
  - Group `westadmins` with their own set of permissions.
  - A mask entry regulating the maximum permissions.

<br>

## Summary

- **ACLs in Linux**: Provide enhanced permission management for complex scenarios where standard permissions are insufficient.
- **Advantages**: Greater control over permissions for different users and groups, enabling adherence to specific security policies.
