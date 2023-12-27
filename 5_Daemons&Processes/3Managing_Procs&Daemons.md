# Managing Linux Processes and Daemons

<br>

## Overview of Linux Processes and Daemons

- **Processes**: Programs or commands executed in Linux. Each process has a unique Process ID (PID).
- **Daemons**: Background services or processes that run continuously, like web servers (Apache) or SSH daemons.

<br>

## Common Commands for Process Management

1. **`ps` Command**:
   - Usage: Displays currently running processes.
   - Example: `ps` shows processes related to the current user session. `ps axu` shows all system processes.

2. **Understanding `ps` Output**:
   - **PID**: Unique identifier for each process.
   - **TTY**: Terminal associated with the process.
   - **CMD**: Command that initiated the process.

3. **`top` Command**:
   - Usage: Dynamically displays running processes and their resource usage.
   - Features: Updates process information periodically (default every 3 seconds).
   - Customization: Press 'F' to choose which fields (columns) to display.

4. **`pstree` Command**:
   - Usage: Shows processes in a tree-like structure.
   - Example: `pstree` displays the hierarchy of processes. `pstree -p` includes PIDs in the tree.

<br>

## Managing Process Lifecycle

- **Killing Processes**:
  - `kill` Command: Terminates a process. Default behavior tries to shut down gracefully.
  - Example: `sudo kill [PID]` ends the process with the specified PID.
  - Forceful Termination: `kill -9 [PID]` immediately stops the process.

- **Analyzing Processes**:
  - Filtering Process List: Use `ps` piped with `grep` to filter processes by criteria (e.g., `ps axu | grep apache`).
  - Identifying Resource Hogs: Utilize `top` to monitor processes consuming excessive resources.

<br>

## Daemon Management

- **Startup Scripts**: Located in `/etc/init.d`, define how to start, stop, and manage services.
- **Runlevel Scripts**:
  - Found in `/etc/rc[runlevel].d`.
  - Scripts starting with 'S' enable daemons, and 'K' scripts disable them in the specified runlevel.

<br>

## Managing Services with systemctl

- **Enabling/Disabling Services**: Control whether services start at boot.
  - Example: `sudo systemctl enable apache2` to start Apache at boot, `sudo systemctl disable apache2` to prevent it from starting.

<br>

## Managing Runlevels

- **Changing Runlevels**: `sudo init [runlevel]` changes the current runlevel.
- **Default Runlevel**: Set the default runlevel using `sudo systemctl set-default [target]`.
  - Example: `multi-user.target` for runlevel 3, `graphical.target` for runlevel 5.

<br>

## Summary

- **Process and Daemon Management**: Key aspect of Linux system administration.
- **Tools and Commands**: Utilize `ps`, `top`, `pstree`, and `systemctl` for effective management.
- **Understanding Runlevels**: Essential for configuring what services run at different stages of the boot process.
