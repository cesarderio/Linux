# Storage and File Systems

<br/>

## Linux Storage Concepts

<br/>

### Mass Storage Devices

In Linux, mass storage devices are referenced under the `/dev` directory. Examples include:

- `/dev/sda`
- `/dev/sdb`

Partitions on these devices start numbering at 1, for example:
- `/dev/sda1`
- `/dev/sdb1`

<br/>

### Disk Initialization Types

- **MBR (Master Boot Record):** Supports a maximum partition size of 2TB and a maximum of 4 partitions.
- **GPT (GUID Partition Table):** Offers no practical limits on disk size or the number of partitions.

**Note:** For software RAID (Redundant Array of Independent Disks), use `fdisk` to set the partition type to Linux RAID autodetect (Press 't', then 'fd').

<br/>

### Common Linux File System Types

- `ext2`, `ext3`, `ext4`: Extended file systems.
- `XFS`: A high-performance 64-bit journaling file system.
- `Reiser4`: Known for its efficiency with small files and metadata-intensive operations.

<br/>

### Linux Storage Management Tools

- `lsblk`: Lists block devices.
  - `lsblk --scsi`: Lists SCSI devices and shows how they are utilized.
- `fdisk`: Used for disk partitioning.
- `mkfs`: Creates a file system.
  - `mkfs.reiser4`: Specific for creating a Reiser4 file system.
- `mount`: Mounts a file system at a specified directory (mount point).

<br/>
<br/>

## The Linux File System Hierarchy

<br/>

### Filesystem Hierarchy Standard (FHS)

The FHS defines the standard directory structure for UNIX and Linux operating systems. While some Linux distributions may have slight variations, they generally follow this structure.

<br/>

#### Directory & Description

- `/`: Root filesystem; the base of the file system hierarchy. All files and directories from various storage devices are accessible here.
- `/bin/`: Contains essential binary command files such as `passwd`, `cat`, `grep`.
- `/boot/`: Holds boot loader files, typically for GRUB (GRand Unified Bootloader).
- `/dev/`: Device files, including those for hardware and special files like random number generators.
- `/etc/`: System-wide configuration files.
- `/home/`: User home directories, including the home directory of the root user.
- `/lib/`: Library files supporting system commands and services.
- `/media/`: Mount point for removable storage media.
- `/mnt/`: Temporary mount points for mounting file systems.
- `/var/`: Variable data files such as logs, spools, and temporary e-mail files.
- `/opt/`: Optional application software packages.
- `/sbin/`: Essential system binaries, e.g., `fdisk`, `useradd`, `mkfs`.
- `/srv/`: Service data such as data for FTP, HTTP servers.
- `/tmp/`: Temporary files, often cleared on reboot.
- `/usr/`: Secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications.
- `/proc/`: Virtual filesystem providing process and kernel information as files.

<br/>

#### FAQ

1. **Why are there `/media` and `/mnt` directories?**
   - `/media`: This directory is typically used for mounting removable media like CDs, DVDs, and USB drives. It's meant for temporary media attached to the system.
   - `/mnt`: Historically used as a temporary mount point for mounting file systems, such as network file systems or additional hard drives. It's more of a generic mount point.

2. **What's the difference between `/bin` and `/sbin`?**
   - `/bin`: Contains essential command binaries that need to be available for all users. These commands are used frequently and are necessary for the system to function properly.
   - `/sbin`: Contains system administration binaries. These are essential for booting, restoring, recovering, and/or repairing the system in addition to the commands in `/bin`.

3. **How do `/opt` differ from `/bin` and `/sbin`?**
   - `/opt`: This directory is reserved for the installation of add-on application software packages. It's a place for software that's not part of the default installation.
   - `/bin` and `/sbin`: These directories are for essential user and system binaries, respectively, and are part of the base system.
