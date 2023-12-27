# Disk Management

## Managing and Repairing Linux File Systems

<br/>

### Using `fsck` (File System Check)

- **Purpose**:
  - To check and repair Linux file systems.
  - Essential for ensuring file systems are not corrupt, which can prevent mounting.

- **Using `fsck`**:
  - Run as `sudo fsck /dev/sdX`, where `/dev/sdX` is the partition.
  - The command should point to a specific partition (e.g., `/dev/sdb1`), not just a device.
  - Error messages may occur if run on a device instead of a partition.

- **Behavior on Mounted File Systems**:
  - `fsck` cannot run on mounted file systems as it could lead to data corruption.
  - If a file system is mounted, `fsck` will abort with an error.

- **Exit Status**:
  - The exit status returned by `fsck` is crucial, especially for scripting.
  - Status includes information like file system errors corrected, the need for a reboot, etc.

- **Automatic Checks at Boot Time**:
  - Configured in `/etc/fstab`.
  - The sixth column in `fstab` indicates if `fsck` should check the file system at boot (0 = no, 1 = yes for root file system, 2 = yes for others).
  - `man 5 fstab` provides more details on `fstab` configuration.

<br/>

### Using `tune2fs`

- **Purpose**:
  - To adjust various parameters of ext2, ext3, and ext4 file systems.

- **Viewing File System Information**:
  - `sudo tune2fs -l /dev/sdX` lists detailed information about the file system.
  - Useful for checking the file system state, among other attributes.

- **Setting Volume Labels**:
  - Volume labels can be assigned for easier identification of file systems.
  - Example: `sudo tune2fs -L MyLabel /dev/sdb1` sets the label 'MyLabel' to `/dev/sdb1`.

- **Scheduling File System Checks**:
  - `tune2fs` can be used to schedule regular file system checks.
  - Example: `sudo tune2fs -i 1w /dev/sdb1` sets the file system on `/dev/sdb1` to be checked once a week.

<br/>

### Summary

- **`fsck`**:
  - Used for checking and repairing file systems.
  - Cannot operate on mounted partitions.
  - Automated checks can be configured via `/etc/fstab`.

- **`tune2fs`**:
  - Alters settings of ext file systems.
  - Can assign volume labels and schedule automated checks.
  - Provides detailed information about the file system.

