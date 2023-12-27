# Understanding Linux Processes and Daemons

<br>

## Linux Processes Overview

- **Definition**: A Linux process is a running instance of a program. It could be a command executed in the terminal or any application running on the system.
- **Process ID (PID)**: Each process is assigned a unique PID by the Linux kernel for identification and management.
- **Types of Processes**:
  - **Regular Processes**: Execute specific tasks like a command in the terminal and may run for various durations.
  - **Daemons**: Background services that run continuously, such as web servers (Apache) or SSH daemons.

<br>

## Understanding Daemons

- **Definition**: Daemons are special types of processes that run in the background, often providing essential services.
- **Characteristics**:
  - Persistent operation.
  - Usually do not have a direct user interface.
  - Often start during the system boot and run as services.
- **Examples**: Apache web server (listens on ports 80/443), SSH daemon (listens on port 22).

<br>

## Managing Processes

- **Viewing Processes**: Use the `ps` command to display running processes. The `-aux` flag shows all processes, including those not tied to a terminal.
- **Understanding Process Output**: The output shows the user, PID, CPU and memory usage, TTY (terminal), and the command that started the process.

<br>

## Process Control

- **Killing Processes**: The `kill` command followed by a PID terminates a process. Using `kill -9` forces a process to stop immediately.
- **Using `pstree`**: Displays a hierarchical view of running processes, starting from the `init` process.
- **Monitoring Processes**: The `top` command shows processes consuming the most system resources.

<br>

## Runlevels and Daemon Management

- **Runlevels**:
  - **Runlevel 3**: Multi-user mode with network support but no GUI.
  - **Runlevel 5**: Similar to Runlevel 3 but with GUI support.
- **Managing Daemons**: Daemons are associated with specific runlevels and have startup scripts in directories like `/etc/init.d`.
- **Daemon Scripts and Runlevels**: Startup scripts in `/etc/rc[runlevel].d` control daemon behavior in different runlevels. Scripts starting with 'S' enable daemons, while 'K' disables them.

<br>

## Using `service` Command

- **Function**: Manages the status of daemons.
- **Usage**: `sudo service [daemon] [command]`, where `[command]` could be `start`, `stop`, `restart`, `status`, etc.
- **Example**: `sudo service ssh status` checks the status of the SSH daemon.

<br>

## Summary

- **Processes and Daemons**: Fundamental to Linux operations, ranging from simple commands to complex services running in the background.
- **Monitoring and Control**: Tools like `ps`, `pstree`, `top`, and `service` provide essential insights and control over Linux processes and daemons.
- **Daemon Configuration**: Understanding daemon management in different runlevels is crucial for system administrators.
