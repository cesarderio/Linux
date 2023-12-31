# Managing SELinux Users on Ubuntu Linux

<br>

## Introduction to SELinux User Management

SELinux (Security-Enhanced Linux) enhances security by providing a framework for mandatory access control. In this demonstration, we explore how regular Linux user accounts can be mapped to SELinux users, thereby controlling their access to system resources based on SELinux policies.

<br>

### Basic Commands and Modes

1. **Checking SELinux Mode**: Use `getenforce` to check the current SELinux mode. `Permissive` mode monitors but does not enforce SELinux policies, while `Enforcing` mode actively enforces them.
2. **Switching SELinux Mode**: Switch to enforcing mode using `sudo setenforce 1`. This impacts user access based on SELinux policies.

<br>

### Mapping Linux Users to SELinux Users

1. **Viewing SELinux User Mappings**: Use `sudo semanage user -l` to list SELinux users and their associated levels.
2. **Checking Current User Mappings**: Use `sudo semanage login -l` to view current mappings of Linux users to SELinux users.
3. **Adding User Mappings**: Map a Linux user to an SELinux user with `sudo semanage login -a -s [SELinux_user] [Linux_user]`. For example, mapping user `cblackwell` to `staff_u`.
4. **Testing SSH Access**: Verify SSH access after mapping. If unmapped, users might be denied SSH access in enforcing mode.
5. **Removing User Mappings**: Remove a user mapping with `sudo semanage login --delete -s [SELinux_user] [Linux_user]`.

<br>

### Practical Considerations

- **SELinux Modes Impact**: User access can vary significantly between permissive and enforcing modes. Always test user access in both modes.
- **Mapping Sensitivity**: Incorrect mappings or unmapped users in enforcing mode can lead to access issues, such as SSH login failures.
- **Context Awareness**: Understanding SELinux contexts (user, process, file) is crucial for effective SELinux management.
- **Unconfined Users**: The `unconfined_u` SELinux user typically faces fewer restrictions, suitable for administrative purposes or when less stringent controls are desired.

<br>

## Conclusion

Managing SELinux users involves mapping Linux users to appropriate SELinux user profiles, ensuring users have the necessary access rights based on organizational security policies. This process is integral to maintaining a secure Linux environment, particularly when operating in enforcing mode. Regularly reviewing and updating user mappings and understanding the implications of SELinux modes are essential for effective SELinux administration.
