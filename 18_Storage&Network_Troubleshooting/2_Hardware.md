# Troubleshooting Storage and Network Hardware in Linux

<br>

## Planning and Compatibility

- **Linux Distribution Compatibility**: Check hardware compatibility with specific Linux distributions (e.g., Ubuntu certified hardware).
- **Hardware Planning**: For physical servers, plan hardware configurations compatible with the Linux distribution.

<br>

## Virtual Machine Hardware Configuration

- **VMware Workstation**: Edit virtual hardware settings for Ubuntu Linux virtual machines, including disk and memory configurations.
- **Resource Adjustments**: Modify virtual machine settings to address performance issues.

<br>

## Kernel Log Analysis

- **Kernel Messages (dmesg)**: Use `sudo dmesg | more` to view kernel log for hardware detection and errors.
- **Hardware Detection**: Look for messages indicating recognition of CPUs, storage devices (e.g., sda, sdb), network interfaces (e.g., eth0).

<br>

## Storage Troubleshooting

- **Disk Space Analysis**: Use `df -h` to check filesystems' disk space usage.
- **Block Devices**: `lsblk --scsi` lists detected SCSI devices.
- **Disk Partitioning**: `sudo fdisk -l /dev/sdc` shows partition details on specific devices.
- **Filesystem Mounting**: Check `/etc/fstab` for persistent mount points and configurations.
- **Mount Command**: Verify currently mounted filesystems and their properties.
- **Filesystem Checks**: Use `sudo fsck /dev/sdd1` for filesystem integrity checks.

<br>

## Network Troubleshooting

- **Network Interface Analysis**: Utilize `grep` with `dmesg` to filter for specific network interfaces.
- **Monitoring Network Configuration**: Check configuration files and command outputs for network settings.

<br>

## Booting and Recovery

- **Alternative Booting Methods**: Ensure access to alternative boot methods (e.g., installation media, USB boot) for troubleshooting unbootable systems.
