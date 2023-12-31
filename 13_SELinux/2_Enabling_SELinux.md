# Enabling SELinux on Ubuntu Linux: A Step-by-Step Guide

<br>

## Introduction to SELinux on Ubuntu

SELinux, or Security-Enhanced Linux, offers a robust mandatory access control system that enhances security by assigning labels and contexts to system resources. In this demonstration, we'll enable SELinux on Ubuntu Linux, a process that varies from other distributions.

<br>

### Initial Setup and Package Installation

1. **Stop and Disable AppArmor**: Run `sudo service apparmor stop` and `sudo systemctl disable apparmor`. AppArmor is a similar security solution to SELinux but needs to be disabled for SELinux installation.

2. **Update Repositories**: Use `sudo apt update` to ensure the latest software packages are available.

3. **Install Necessary Packages**: Install SELinux packages with `sudo apt install policycoreutils selinux-utils selinux-basics`.

<br>

### Configuring SELinux

1. **Checking Status**: After installation, check SELinux status using `sudo sestatus` and `sudo getenforce`. Initially, it will be disabled.

2. **Edit Configuration File**: To view current SELinux configuration, use `sudo cat /etc/selinux/config | more`. The configuration is initially set to permissive mode.

3. **Activate SELinux**: Activate SELinux using `sudo selinux-activate` and reboot the system with `sudo init 6`.

4. **Verify Changes**: Post-reboot, recheck the status with `sudo sestatus` and `sudo getenforce`. The status should now be enabled and permissive.

5. **Enforce SELinux Policies**: To switch to enforcing mode, use `sudo setenforce 1` and verify with `sudo getenforce`.

<br>

### Important Considerations

- **Reconfiguration**: Modify `/etc/selinux/config` to set SELinux to enforcing mode permanently. However, ensure proper configuration before enforcing to avoid system lockouts.

- **User Mapping and Contexts**: Proper configuration of user mappings and context settings is crucial to prevent system access issues, especially when enabling enforcing mode.

<br>

## Conclusion

Activating SELinux on Ubuntu Linux significantly enhances system security by controlling access based on predefined policies. While the process involves several steps, including disabling competing systems like AppArmor and installing necessary packages, the result is a more secure and controlled environment. It's crucial to proceed with caution, particularly when switching to enforcing mode, as incorrect configurations can lead to system access issues. Proper understanding and configuration of SELinux are essential for its effective use in securing Ubuntu Linux systems.
