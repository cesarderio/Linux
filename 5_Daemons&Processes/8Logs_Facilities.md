# Monitoring Linux System Performance with Linux Logging Facilities

<br>

## Overview of Linux Logging Facilities

- **Log Location**: Most Linux distributions store logs in `/var/log`.
- **System Log**: In Ubuntu, the main system log is named `syslog`, located in `/var/log`.
- **Log Filtering**: Essential for isolating relevant information from extensive log files.

<br>

## Log Filtering Techniques

1. **Using Sed for Filtering**:
   - Example: `sed -e '/cron/d' /var/log/syslog` filters out entries containing 'cron'.
   - Regular expressions can help target specific log entries.

2. **Other Methods**: Various command-line tools are available for filtering and extracting log data.

<br>

## Monitoring User Activity with Logs

- **Last Log Command**:
  - Displays last login information for user accounts.
  - Example output: `cblackwell pts/1 192.168.2.11 Sun Jun 12:02:21 +0000 2023`.

<br>

## Kernel Log Messages

- **Dmesg Command**:
  - Shows messages from the Linux kernel.
  - Useful for troubleshooting hardware and driver-related issues.
  - Example usage: `dmesg | grep USB` to filter for USB device messages.

<br>

## Understanding Log Rotation

- **Purpose**: Manages log file sizes by periodically archiving and removing old log data.
- **Configuration**: Defined in `/etc/logrotate.conf`.
- **Logrotate Tool**:
  - Rotates logs based on specified criteria like size, age, or frequency.
  - Options: `missingok`, `daily`, `rotate`, `notifempty`, `compress`.
- **Example**: Configuring Apache logs in `/etc/logrotate.d/apache2.conf`.
  - Set to rotate daily, keep three versions, compress older logs.

<br>

## Managing Log Rotation

- **Forcing Log Rotation**: Use `logrotate -d /etc/logrotate.d/apache2.conf` to test rotation.
- **Automation**: Often scheduled as a cron job for daily execution.

<br>

## Importance of Logs

- **Compliance**: Ensure logs are retained according to regulations and policies.
- **Centralized Logging**: Storing logs on a dedicated server for backup and analysis.

<br>

## Summary

- **Linux Logs**: Provide crucial insights into system performance and issues.
- **Log Management**: Involves filtering, monitoring, and rotating logs to maintain system health.
- **Tools and Commands**: Various utilities like `sed`, `last`, `dmesg`, and `logrotate` assist in log management.
