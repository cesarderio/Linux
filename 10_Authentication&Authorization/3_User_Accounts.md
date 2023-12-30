# Working with User Accounts in Linux

<br>

## Introduction

This guide will demonstrate how to manage user accounts in Linux, using both graphical user interface (GUI) and command line methods.

<br>

### Managing User Accounts via GUI (Ubuntu Desktop Example)

**Accessing User Management**:
- Open the menu and search for "user".
- Navigate to "Users" in the Settings to manage user accounts.

**User Management Features**:
- Change password for current user.
- View account activity.
- Add or remove user accounts after unlocking with administrative privileges.

**Adding a User**:
- Click "Add User" and enter the full name; the system generates a username.
- Choose between standard and administrative user types.
- Set password options.

<br>

### Managing User Accounts via Command Line

**Adding a User with Command Line**:
- Use `sudo useradd -m -g` to create a user with a home directory and specify a primary group.
- If the group doesn't exist, create it with `sudo groupadd`.
- Set a password for the new user with `sudo passwd`.

**Viewing User Information**:
- Use `tail /etc/passwd` to view user details, including user ID and default shell.
- Use `tail /etc/shadow` to view encrypted user passwords.

<br>

### Advanced User Management Commands

**File Permissions and Ownership**:
- Change file ownership with `sudo chown`.
- Adjust permissions with `chmod`.

**Group Management**:
- Add groups with `sudo groupadd`.
- Modify user group memberships using `sudo usermod`.
- Use `tail /etc/group` to view group details.

**Switching Users**:
- Use `su - [username]` to switch to another user account within a session.

<br>

### Removing a User

- Use `sudo userdel [username]` to delete a user account.

<br>

## Conclusion

This guide covers the essential tasks for managing user accounts in Linux, both through a graphical interface and command line. Understanding these methods is vital for effective Linux system administration.
