# Using Systemd for Scheduling Tasks in Linux

<br>

## Introduction

- **Context**: Systemd is increasingly used for scheduling tasks in Linux, offering more features than traditional CRON jobs.
- **Use Cases**: For scheduling tasks like clean-up operations or running custom scripts.

<br>

### Systemd Timer Units: An Overview

- **Advantages**: Offers additional features like delayed execution after an event.
- **Viewing Default Timers**:
  - Command: `sudo systemctl status *timer`
  - Output: List of systemd timers with `.timer` suffix, showing active status and triggers.

<br>

### Creating Custom Timer Unit

1. **Creating Service Unit**:
   - Navigate: `/etc/systemd/system`
   - Command: `sudo nano test1.service`
   - Content: Define a simple service unit with description, service type, and execution command.

2. **Checking Service Status**:
   - Command: `sudo systemctl status test1.service`
   - Output: Displays the status of the custom service.

3. **Verifying Execution**:
   - Command: `journalctl -S today -u test1.service`
   - Outcome: Checks if the specified command (`free`) executed successfully.

4. **Configuring Timer Unit**:
   - Command: `sudo nano test1.timer`
   - Details: Create a timer unit linked to the service (`test1.service`).
   - Scheduling: Set `OnCalendar` for desired frequency (e.g., every minute).

5. **Linking Service and Timer**:
   - Edit `test1.service` to include `Wants=test1.timer`.
   - Ensures a connection between the service and its timer.

6. **Restarting and Monitoring Service**:
   - Command: `sudo systemctl restart test1.service`
   - Real-time Monitoring: `journalctl -f -u test1.service`
   - Observes the service executing at the set intervals.

<br>

### Key Takeaways

- **Systemd vs CRON**: Systemd provides a modern approach to scheduling tasks with enhanced control and capabilities.
- **Troubleshooting Considerations**: Be aware of systemd timers as a potential source of scheduled tasks, which might be overlooked if expecting CRON jobs.
- **Practical Use**: Ideal for scenarios requiring specific timing and dependencies between tasks.

<br>

## Conclusion

Systemd timers offer a robust and flexible alternative to traditional CRON jobs in Linux. Their ability to handle complex scheduling needs and integration with systemd services makes them a valuable tool for modern Linux systems administration and troubleshooting.
