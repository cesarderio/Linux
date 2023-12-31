# Basic SELinux Configuration on Ubuntu Linux

<br>

## Introduction to SELinux Configuration

SELinux (Security-Enhanced Linux) provides a mandatory access control system that significantly enhances Linux security. This demonstration covers the basics of SELinux configuration, focusing on file contexts and initial setup.

<br>

### Enabling and Configuring SELinux

1. **Accessing SELinux Config File**: Use `sudo nano /etc/selinux/config` to view and edit SELinux settings. The default mode is typically set to permissive.
2. **Switching Modes**: Change SELinux mode from permissive to enforcing with `sudo setenforce 1`. Use `sudo getenforce` to verify the current mode.
3. **Mapping Linux to SELinux Users**: Ensure proper mapping of Linux users to SELinux users to prevent issues like SSH login problems.

<br>

### Managing SELinux Contexts

1. **Viewing User Context**: Check your SELinux user context with `id -Z`. This displays your user, role, and permission levels.
2. **Viewing Process Contexts**: Use `ps -auxZ` to view the SELinux context of running processes. For specific processes (e.g., Apache), use `ps -auxZ | grep apache`.
3. **File System Contexts**: Navigate to a directory (e.g., `/var/www/html`) and use `ls -Z` to view file contexts. The Apache index file typically has a context type of `httpd_sys_content_t`.
4. **Changing File Contexts**: Create a new directory and file (e.g., `sudo mkdir /site1` and `sudo touch /site1/index.html`). Change the context using `sudo chcon -R -t httpd_sys_content_t ./site1`.

<br>

### Practical SELinux Management

- **SELinux Modes**: Understand the implications of SELinux modes:
  - **Disabled**: SELinux is turned off.
  - **Permissive**: SELinux is active but not enforcing policies (useful for monitoring).
  - **Enforcing**: SELinux actively enforces configured policies.

- **Configuring SELinux**: Edit `/etc/selinux/config` to set the desired SELinux mode. Remember to reboot for changes to take effect.

<br>

## Conclusion

Configuring SELinux involves setting the appropriate mode, understanding user and process contexts, and managing file contexts. While SELinux adds a layer of complexity to system administration, its benefits in enhancing security make it a valuable tool for Linux systems. Remember to proceed with caution when switching to enforcing mode and ensure correct user and process mappings to avoid system access issues. Regular review and management of SELinux policies and contexts are crucial for maintaining a secure Linux environment.
