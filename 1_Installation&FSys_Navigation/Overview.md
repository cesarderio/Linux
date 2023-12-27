# Linux Overview:

- **Linux based on Unix**: Linux is a Unix-like operating system, sharing similar concepts and design philosophy.
- **Developed by Linus Torvalds in the early 1990s**: Created as an open-source alternative to Unix.
- **Many different flavors (distros)**: Varieties of Linux, each with unique features and designs, are available.
- **Used in servers, workstations, desktops, and GUI environments**: Linux is versatile, suitable for various applications from server environments to graphical user interfaces.

- **Consists of key components**:
    - ***Kernel***: Referred to as the "Heart" of Linux, it's the core part of the OS, managing system resources and hardware.
    - ***Libraries***: These are "Shared Libraries" or "Library Files" that provide common code that can be used by multiple programs.
    - ***Configuration Files***: These files store system and application settings.
    - ***Daemons***: These are "Background running programs", similar to services in Windows, performing tasks in the background.
    - ***Command line shells and GUI***: Interfaces for interacting with the system, including both command line interfaces like Bash and graphical interfaces.

<br>

## Kernel:

- **Heart of the Linux OS**: The kernel manages and mediates interactions between hardware and software.
- **View kernel version details with `uname -a`**: This command displays detailed information about the kernel.
- **The kernel starts the "/sbin/init" process first**: This is the initial process started by the kernel, crucial for the boot process.

<br>

## Library Files:

- **Found under "/var/lib"**: This directory commonly contains library files.
- **In Linux, the color blue usually means it is a directory/subdirectory**: A visual cue in many command-line interfaces to distinguish directories.

<br>

## Configuration Files:

- **Found in /etc/**: This is a standard directory for system configuration files.
- **Normally text files editable with tools such as vi/vim or nano**: These are common text editors used in the Linux environment.
- **Most end in ".conf"**: A conventional extension for configuration files.
- **Changes to .conf files usually mean restarting the related daemon**: This is necessary for the daemon to read and apply the new configurations.
- **Some daemons allow you to "reload" them**: This can apply changes without needing a full restart.
- **Installed packages may have more than one config file**: Indicating multiple configuration aspects.

<br>

## Daemons:

- **Background running processes not tied to a user terminal**: They perform various tasks silently in the background.
- **Usually started by the system or service manager**: Similar to how Windows services operate.
- **Can be controlled with the "service" command**: For example, `service sshd status; service sshd start/stop` manages the SSH daemon.

<br>

## Command Line Shells:

- **Include Bash, Korn, C, zsh**: Different shells for user preference in scripting and command-line interaction.

<br>

## GUI:

- **Based on X-Windows**: A windowing system for bitmap displays.
- **Started with `startx` command**: This command initiates the graphical interface.
- **Remote X forwarding**: Allows GUI applications to be run on a remote server but displayed locally.

<br>

## Linux Distributions:

- **Distros are variants of the Linux OS**: These are different versions of Linux, each with unique characteristics and designed for various purposes.
- **Based on Debian, Red Hat, and SUSE**: These are the foundational families from which many distros derive. Each family offers a different approach and package management system.
- **Specialized for different sectors**: Some distros are tailored for specific uses, such as industrial applications, multimedia production, or security and penetration testing.
- **Why So Many different distros?**: The Linux Kernel is open-source and free, allowing for the development of an entire OS without licensing costs. This freedom encourages innovation and customization.
- **Many new distributions are based on existing ones**: It's common to build new distros by modifying and adapting existing ones.
- **Variations in GUI and software packages**: Distros can differ significantly in their user interface (e.g., GNOME vs. KDE) and the software packages they include by default.

Examples of Distros:
- **Debian**: Known for its stability and large software repository.
- **Ubuntu**: Popular for its ease of use and strong community support.
- **Fedora**: Known for featuring cutting-edge technology.
- **Arch Linux**: Appeals to experienced users who prefer a do-it-yourself approach.
- **Peppermint**: Lightweight and user-friendly, suitable for older hardware.
- **Kali Linux**: Specialized for penetration testing and security auditing.
- **CentOS**: Favored for servers due to its stability and long-term support.
- **Pop!_OS**: Developed by System76, optimized for their hardware but usable on others.

Specialized Distros:
- **Kali Linux**: Focused on Penetration Testing and security.
- **64Studio**: Tailored for Video & Media Production.
- **AsteroidOS**: Designed for smartwatches.
- **Audiophile**: Optimized for high-quality music playback.
- **Apertis**: Developed for vehicle infotainment systems.
- **Raspbian**: Customized for Raspberry Pi devices.
