# Configuring Linux Daemon Startup Scripts

<br>

## Overview of Linux Daemons

- **Daemons**: Background programs that run continuously, providing various services like web servers or scheduled tasks.
- **Startup Scripts**: Control the automatic startup of these daemons in different runlevels.

<br>

## Managing Apache Web Server Daemon

1. **Checking Daemon Status**:
   - Use `sudo service apache2 status` to check if the Apache server is active or inactive.

2. **Starting the Daemon**:
   - Start the Apache server with `sudo service apache2 start`.
   - Verify its active status and note the service file path and status (enabled/disabled).

3. **Daemon Configuration File**:
   - Located at `/lib/systemd/system/apache2.service`.
   - Contains directives like `ExecStart` for starting the daemon and dependencies like `After`.

4. **Daemon Startup in Runlevels**:
   - Scripts in `/etc/rc[runlevel].d` control daemon behavior in different runlevels.
   - Example: `/etc/rc3.d` contains scripts for runlevel 3.
   - `S01apache2` script in `/etc/rc3.d` is a symlink to the actual startup script in `/etc/init.d`.

5. **Inspecting Startup Scripts**:
   - Navigate to `/etc/init.d` and examine the daemon's script (e.g., `cat apache2`).
   - Scripts check for valid configuration and control daemon startup.

6. **Enabling/Disabling Daemons**:
   - Use `sudo update-rc.d apache2 disable` to prevent Apache from starting in a specific runlevel.
   - Verify changes by checking the presence of start (`S`) or kill (`K`) scripts in the runlevel directory.

<br>

## Understanding Runlevels

- **Runlevel Concept**: Defines different states of the system, each with specific services and daemons active.
- **Checking Current Runlevel**: Use the `runlevel` command.
- **Switching Runlevels**: Change runlevels with `sudo init [runlevel_number]` (e.g., `sudo init 5` for GUI mode).

<br>

## Summary

- **Daemon Management**: Essential for controlling background services and ensuring system stability.
- **Runlevel Scripts**: Determine which services start or stop in each runlevel.
- **Systemd and Init.d**: Modern Linux systems use systemd, but scripts in `/etc/init.d` are still relevant for service management.
- **Customization**: Administrators can customize daemon behavior at startup by modifying or disabling startup scripts.
