# Managing Linux Groups from the Command Line

<br>

## Introduction

This guide covers managing Linux groups via command line, demonstrating various tasks from group creation to deletion.

<br>

### Viewing Existing Groups

- **Command**: `sudo tail /etc/group`
- **Output**: Displays a list of groups, with details like group ID.

<br>

### Creating a New Group

- **Command**: `sudo groupadd [groupname]`
- **Example**: Create a group named `linuxadmins`.
- **Verification**: `tail /etc/group` shows the newly created group.

<br>

### Adding a User to a Group

- **During User Creation**:
  - **Command**: `sudo useradd -m -g [groupname] [username]`
  - **Example**: Assign user `jgold` to `linuxadmins` group.

- **After User Creation**:
  - **Command**: `sudo usermod -g [groupname] [username]`
  - **Example**: Change `jgold`'s group to `eastadmins`.

<br>

### Adding a User to Multiple Groups

- **Command**: `sudo usermod -aG [group1,group2,...] [username]`
- **Example**: Add `jgold` to both `linuxadmins` and `fulltimers` groups.
- **Note**: `-aG` appends groups without altering the primary group.

<br>

### Modifying Group Attributes

- **Renaming a Group**:
  - **Command**: `sudo groupmod -n [newname] [oldname]`
  - **Example**: Rename `fulltimers` to `fulltimeemployees`.

- **Removing a User from a Group**:
  - **Command**: `sudo gpasswd -d [username] [groupname]`
  - **Example**: Remove `jgold` from `fulltimeemployees`.

<br>

### Deleting a Group

- **Command**: `sudo groupdel [groupname]`
- **Example**: Delete the `fulltimeemployees` group.

<br>

## Conclusion

This guide provides a comprehensive overview of managing Linux groups through command line operations. Understanding these commands is crucial for effective Linux system administration, especially in multi-user environments.
