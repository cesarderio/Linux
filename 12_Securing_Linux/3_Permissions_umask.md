# Configuring Umask in Linux for Enhanced File Permissions

<br>

## Introduction to Umask

In Linux, the `umask` (user file creation mode mask) command controls the default file and directory permissions set by the kernel during their creation. By configuring `umask`, users can subtract permissions from the system's default settings.

<br>

### How Umask Works

- **Default Kernel Permissions**: Typically, Linux assigns `666` (read-write) permissions for files and `777` for directories.
- **Umask Setting**: The `umask` value specifies which permissions to subtract from the defaults. For example, a `umask` of `022` would result in new files having `644` permissions (read-write for owner, read-only for others).

<br>

### Demonstration of Umask in Action

- **Default Umask Value**: The standard `umask` value is usually `002`, affecting the permissions given to 'others'.
- **Creating Files with Umask**: Using `touch` to create a file, the permissions are automatically set based on the `umask` value.

  [Video description begins] The presenter demonstrates creating a new file and checking its permissions. The output shows permissions set according to the `umask` value. [Video description ends]

- **Adjusting Umask Value**: By changing the `umask` value (e.g., to `006`), subsequent files created will have permissions adjusted accordingly.

<br>

### Changing Umask Permanently

- **Modifying Umask for Future Sessions**: Users can set a default `umask` value in their `.bashrc` file.
- **Procedure to Set Umask**:
  1. Edit `.bashrc` file (`sudo nano .bashrc`).
  2. Add the desired `umask` setting (e.g., `umask 0006`) at the end of the file.
  3. Save and exit (`Ctrl+X`).

<br>

### Testing Umask Changes

- **Re-login to Apply Changes**: Use `su -` to re-login and verify the new `umask` value.
- **Creating Files After Umask Change**: New files will reflect the updated default permissions set by the new `umask`.

<br>

## Conclusion

Configuring `umask` is a straightforward yet powerful way to control default file and directory permissions in Linux. By adjusting `umask`, administrators can enhance security by limiting permissions for new files, helping to protect sensitive data from unauthorized access.
