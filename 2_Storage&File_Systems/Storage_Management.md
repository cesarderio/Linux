# Linux Storage Command Line Management Tools

<br/>

## Common Linux Storage Management Tools

Most of these tools require root privileges. You can use the `sudo` prefix to execute commands with administrative rights. The syntax of these commands may vary slightly between different Linux distributions.

<br/>

### Tool Descriptions and Usage

- **lsblk**
  - Description: Lists block storage devices.
  - Usage: Use the `--scsi` parameter to display only Small Computer System Interface (SCSI) devices.

- **fdisk**
  - Description: Manages disk partitions.
  - Usage: Use the `-l` parameter to list the partitions on a device. This tool is more frequently used with MBR disks.

- **mkfs**
  - Description: Formats a partition with a specified filesystem (e.g., ext4, ReiserFS).
  - Usage: Typically used as `mkfs -t [type] [device]`, where `[type]` is the filesystem type (e.g., `ext4`, `xfs`) and `[device]` is the partition (e.g., `/dev/sda1`).

- **parted**
  - Description: A versatile tool for managing disk partitions, including creating, resizing, deleting, and copying partitions.
  - Usage: Supports both MBR and GPT partition tables and is capable of resizing partitions without data loss.

- **partprobe**
  - Description: Instructs the kernel to re-read the partition table of a specified device.
  - Usage: Useful after making changes to partition tables to ensure the system recognizes the changes without rebooting.

<br/>

### Additional Important Tools

- **mount**
  - Description: Mounts a filesystem to a specified directory (mount point).
  - Usage: Used to access the contents of a filesystem.

- **umount**
  - Description: Unmounts a mounted filesystem.
  - Usage: Ensures that changes to the filesystem are written and prevents data corruption.

- **df**
  - Description: Displays disk space usage for the file systems.
  - Usage: Useful for monitoring the amount of free space available.

- **du**
  - Description: Estimates file and directory space usage.
  - Usage: Helpful for identifying how much space individual files and directories are consuming.

<br/>

## Creating Linux File Systems

<br/>

### Tools and Commands for Managing File Systems

1. **Disks Tool (GUI)**
   - Description: A graphical utility for managing disk drives and partitions.
   - Usage: It allows you to format partitions, edit details (like labels and mount options), resize, run checks, repair file systems, and configure mounting options.

2. **Listing File Systems with fdisk**
   - Command: `fdisk -l`
   - Usage: Lists all partitions and their file systems on all disks.
   - Example: `sudo fdisk -l` lists all filesystems.
   - Specific Disk: `sudo fdisk -l /dev/sdb` lists the file system on `/dev/sdb`.

3. **Creating a File System with mkfs**
   - Command: `sudo mkfs -t [type] [device]`
   - Usage: Formats a partition with a specified file system type.
   - Example: `sudo mkfs -t ext4 /dev/sdb1` formats the `/dev/sdb1` partition with the ext4 file system.

4. **Creating a Mount Point**
   - Command: `sudo mkdir /path/to/mount-point`
   - Usage: Creates a directory to serve as a mount point.
   - Example: `sudo mkdir /data1` creates a directory named "data1".

5. **Mounting a File System**
   - Command: `sudo mount [device] [mount-point]`
   - Usage: Attaches the specified file system to the file system hierarchy at the mount point.
   - Example: `sudo mount /dev/sdb1 /data1` mounts the file system on `/dev/sdb1` to the directory `/data1`.

6. **Verifying Mount**
   - Command: `mount | grep [device]`
   - Usage: Checks if the device is mounted and displays its mount details.
   - Example: `sudo mount | grep sdb1` checks if `/dev/sdb1` is mounted and displays its mount information.

<br/>

### Additional Considerations

- **File System Check (fsck)**
  - Used to check and repair inconsistencies in file systems.
  - Run `sudo fsck [device]`, e.g., `sudo fsck /dev/sdb1`.

- **Unmounting File Systems**
  - Use `sudo umount [mount-point]` to safely unmount a file system.

- **Automounting File Systems**
  - Edit `/etc/fstab` to configure file systems to be mounted automatically at boot.

- **Choosing a File System Type**
  - Consider the specific needs (performance, reliability, compatibility) when choosing a file system type (ext4, XFS, Btrfs, etc.).
