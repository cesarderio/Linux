# Resizing Partitions and Managing Filesystems in Linux

<br>

## Using GUI (Graphical User Interface)

- **Access Disk Utility**: Open 'Disks' application from the menu.
- **View Disk Partitions**: Select a disk to view its partitions and details (e.g., partition type, size).
- **Resize Options**:
  - Select a partition.
  - Use the gear icon to access options like 'Format', 'Edit', 'Resize', etc.
  - Resizing can involve extending or shrinking the partition based on available space.

<br>

## Using CLI (Command-Line Interface)

- **Unmount the Partition**: Use `sudo umount /dev/sdb1`.
- **Check Filesystem**: Run `sudo e2fsck -f /dev/sdb1` to check the filesystem integrity.
- **Resize Filesystem**: Use `sudo resize2fs /dev/sdb1 1200M` to resize the partition to 1.2 GB.
- **Verify Changes**: Recheck the partition size in the GUI tool or CLI.

<br>

## Points to Note

- Ensure partitions are not mounted when resizing.
- Always back up data before performing disk operations.
- GUI tools offer a visual and user-friendly approach, while CLI provides more detailed control.
- Compatibility with various filesystem types (e.g., FAT, Linux Filesystem) may vary.

