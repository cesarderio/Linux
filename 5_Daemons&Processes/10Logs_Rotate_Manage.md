# Configuring Linux Log Rotation

<br>

## Overview of Log Rotation in Linux

- **Purpose**: Manage log file sizes and disk space usage.
- **Location**: Log files are generally stored in `/var/log`.
- **Configuration**: Controlled by files in `/etc/logrotate.d` and the global configuration file `/etc/logrotate.conf`.

<br>

## Steps to Configure Log Rotation

1. **Accessing Log Files**:
   - Navigate to `/var/log` to view various log files (e.g., `auth.log`, `syslog`, `dmesg`, and package-specific logs like `apache2`).

2. **Examining Log Rotation Configuration**:
   - Go to `/etc/logrotate.d` to find configuration files for specific services (e.g., `apache2`).
   - Use a text editor (like `nano`) to open and edit these files.

3. **Understanding Configuration Directives**:
   - Log file paths (e.g., `/var/log/apache2/*.log` for Apache logs).
   - Rotation frequency (`daily`, `weekly`, `monthly`).
   - Number of rotations to keep (`rotate` directive, e.g., `rotate 14`).
   - Compression settings (`compress` to use gzip).
   - Creation of new log files after rotation (`create` with permissions).
   - Pre and post-rotation scripts (`prerotate`/`postrotate`).

4. **Global Configuration**:
   - `/etc/logrotate.conf` includes global settings and references `/etc/logrotate.d`.

5. **Executing Log Rotation**:
   - Manually trigger rotation using `logrotate` command with specific config files (e.g., `logrotate -d /etc/logrotate.d/apache2.conf`).

6. **Example: Apache2 Log Rotation Config**:
   - Target log files: `/var/log/apache2/*.log`.
   - Daily rotation with a limit of 14 past logs.
   - Compressed older logs.
   - Special scripts to execute before and after rotation.

<br>

## Summary

- **Effective Log Management**: Crucial for maintaining system health and ensuring compliance with storage policies.
- **Customization**: Log rotation settings can be tailored to meet specific needs and policies of an organization.
- **Command Line Proficiency**: Essential for Linux administrators to manage and configure log rotation effectively.
