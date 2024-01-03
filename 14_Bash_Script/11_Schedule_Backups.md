# Scheduling a Backup Script in Linux

<br>

## Introduction to Scheduling Backups

This demonstration focuses on how to schedule a backup script in Linux, particularly using cron jobs.

<br>

### Understanding Backup Script Permissions

- **Special User ID Bit**: The backup script, `backup.sh`, has the special user ID bit set, indicated by `rwsr-xr-x`, allowing it to run with root permissions.

<br>

### Preparing the Backup Script

- **Script Inspection**: Use `sudo nano` to view and modify the backup script.
- **Removing Weekday Logic**: For cron scheduling, remove any weekday-specific logic from the script.

<br>

### Scheduling with Cron

- **System-wide Cron Jobs**: Explore directories like `cron.daily`, `cron.hourly`, `cron.monthly`, and `cron.weekly` for system-level cron jobs.
- **Editing User Crontab**: Use `crontab -e` to edit an individual user's cron jobs.

<br>

### Setting up Cron Job

- **Cron Syntax**: Understand the cron syntax: minute, hour, day of month, month, day of week, followed by the command.
- **Example Schedule**: Schedule the backup to occur every Saturday at midnight by setting the cron job as `0 0 * * 6 /home/cblackwell/backup.sh`.

<br>

### Testing the Backup Script

- **Manual Testing**: Ensure the backup script functions correctly by running it manually with `./backup.sh`.
- **Function Call Adjustment**: Modify the script to call the backup function directly, ensuring it executes as intended.

<br>

### Understanding Crontab Format

- **Using `man` Command**: Utilize `man 5 crontab` to understand the format and syntax of crontab files.
- **Crontab Fields and Options**: Learn about different scheduling options like using `*` for all values, ranges, or periodic schedules (e.g., `*/2` for every two hours).

<br>

## Conclusion

Scheduling a backup script in Linux requires a combination of proper permissions, understanding cron syntax, and ensuring the script is functional. By leveraging cron jobs, you can automate backups to occur at specific intervals, enhancing data security and management efficiency.
