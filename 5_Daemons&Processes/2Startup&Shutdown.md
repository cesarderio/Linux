# Managing Linux Startup and Shutdown

<br>

## Linux Runlevels Overview

- **Runlevels**: Different states of a Linux system, each with a unique purpose, like shutdown, reboot, multi-user mode, etc.
- **Common Runlevels**:
  - **0**: Shutdown.
  - **3**: Multi-user mode without GUI.
  - **5**: Multi-user mode with GUI.
  - **6**: Reboot.

<br>

## Managing System States

- **Changing Runlevels**: Use the `init` command followed by the runlevel number (e.g., `sudo init 3` to switch to runlevel 3).
- **Current Runlevel**: Determine the current runlevel using the `runlevel` command.
- **Effects of Changing Runlevels**: For example, switching to runlevel 3 from 5 will stop the GUI.

<br>

## Runlevel Directories

- **Location**: `/etc/rc[runlevel].d` directories contain scripts for each runlevel.
- **Scripts**:
  - **Start Scripts**: Prefixed with 'S', determine which daemons start in a runlevel.
  - **Kill Scripts**: Prefixed with 'K', specify daemons to stop.
- **Example**: The `/etc/rc3.d` directory contains scripts for runlevel 3.

<br>

## Installing and Managing Services

- **Installing Services**: Use package managers (e.g., `sudo apt install apache2`) to install services like Apache web server.
- **Service Status**: Check the status of a service using `sudo service [service_name] status`.
- **Enabling/Disabling Services**: Use `sudo systemctl enable/disable [service_name]` to control if a service starts at boot.

<br>

## Managing Service Scripts

- **Service Scripts Location**: `/etc/init.d` contains scripts that define how to start, stop, and manage services.
- **Customizing Service Behavior**: Modify these scripts for custom startup/shutdown behavior of services.
- **Symlink Management**: `systemctl` commands manipulate symlinks in runlevel directories to enable/disable services.

<br>

## Setting Default Runlevel

- **Command**: `sudo systemctl set-default [target]` sets the default runlevel.
- **Targets**:
  - `multi-user.target`: Corresponds to runlevel 3.
  - `graphical.target`: Corresponds to runlevel 5.

<br>

## Summary

- **Runlevel Management**: Understanding and manipulating runlevels is crucial for controlling Linux startup and shutdown behaviors.
- **Service Management**: Knowledge of managing services through systemd and init scripts is essential for system administration.
- **Customization**: Ability to customize service scripts and runlevel configurations provides flexibility in managing Linux systems.
