# Understanding AppArmor in Ubuntu Linux

<br>

## Introduction to AppArmor

AppArmor is a Mandatory Access Control (MAC) system integrated into the Linux kernel, similar to SELinux. It enhances security by restricting the capabilities of processes, such as file system access.

<br>

### Checking AppArmor Status

1. **Command**: Use `sudo apparmor_status` to view active profiles.
2. **Output**: Displays profiles, their modes, and the number of profiles in each mode.

<br>

### Modes of AppArmor

- **Complain Mode**: Functions like SELinux's permissive mode, monitoring and logging actions without enforcing restrictions.
- **Enforce Mode**: Actively restricts processes according to defined profiles, similar to SELinux's enforcing mode.

<br>

### Setting Profiles to Enforce Mode

1. **Command**: `sudo aa-enforce /etc/apparmor.d/*` sets all profiles in the directory to enforce mode.
2. **Installation**: If `aa-enforce` is not found, install `apparmor-utils` using `sudo apt install apparmor-utils`.

<br>

### Monitoring and Adjusting Profiles

- **Observation**: Initially, use complain mode to observe and ensure compatibility.
- **Switching Modes**: Change individual profiles between complain and enforce modes using `sudo aa-complain` or `sudo aa-enforce`.
- **Example**: To set `usr.sbin.tcpdump` to enforce mode, use `sudo aa-enforce /etc/apparmor.d/usr.sbin.tcpdump`.

<br>

### Managing AppArmor Profiles

1. **Editing Profiles**: Use `sudo nano /etc/apparmor.d/profile-name` to view or edit a specific profile.
2. **Custom Profiles**: For custom applications, create tailored profiles to ensure proper functioning under AppArmor's restrictions.

<br>

### Disabling AppArmor

- To prevent AppArmor from starting automatically, execute `sudo systemctl disable apparmor`. This action stops AppArmor from being active after reboot.

<br>

## Conclusion

AppArmor in Ubuntu Linux serves as an effective security tool by managing process capabilities based on predefined profiles. Understanding and managing these profiles, especially in enforce mode, is crucial for maintaining a secure Linux environment. Custom applications may require special attention with tailored AppArmor profiles to function correctly without compromising security. AppArmor, like SELinux, is a vital component of Linux security, offering robust protection through controlled access permissions.
