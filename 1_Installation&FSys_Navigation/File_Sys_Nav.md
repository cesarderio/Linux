# File System Navigation

<br>

## Managing Linux Hardware

- **ls /dev**:
   - This command lists the contents of the `/dev` directory, which is a standard part of the Linux Filesystem hierarchy.
   - This directory is present in all Linux distributions and contains device files representing hardware components.
   - Common device files include `cdrom` for optical drives, `usb` for USB devices, and `sda`, `sdb`, etc., for storage devices.

- **ls /dev/sd?**:
   - This command displays all the mass storage devices recognized by the system, such as hard drives and SSDs.

- **Installing Specialized Drivers**:
   - To install specific hardware drivers, use package management commands. For example, `sudo apt install nvidia-kernel-***` installs Nvidia drivers on Debian-based distributions.

- **ls /proc**:
   - The `/proc` directory contains a pseudo-filesystem that provides an interface to kernel data structures. It is dynamic, reflecting the current state of the kernel.
   - It includes information about processes and system information.

- **cat /proc/cpuinfo**:
   - This command displays detailed information about the CPU, such as its type, make, model, and performance metrics.

- **ls /proc/bus/pci**:
   - Lists PCI bus information, showing what PCI devices are currently recognized by the system.

- **cat /proc/bus/pci/devices**:
   - Displays detailed information about the devices connected to the PCI bus.

- **lspci**:
   - The command `lspci` lists all PCI devices.
   - Using `lspci -v` provides verbose output, showing more detailed information.
   - Piping it to `more`, as in `lspci -v | more`, allows you to view the information one screenful at a time for easier reading.

- **lsusb -v**:
   - Lists USB devices in verbose mode, showing detailed information about each connected USB device.

- **DMI (Desktop Management Interface)**:
   - Provides BIOS or UEFI information.
   - The command `sudo dmidecode` accesses this information and displays it in a readable format.

<br>

## Using Linux File System Navigation Commands

- **pwd**:
   - Stands for "print working directory."
   - This command displays the current directory you are in.

- **cd /etc**:
   - Changes the current directory to the `/etc` directory.
   - `/etc` typically contains configuration files and directories.

- **cd**:
   - Typing `cd` alone will change the directory to your home directory.

- **ls**:
   - Lists the contents of a directory.
   - Similar to the `dir` command in Windows.

- **Directory and File Color Coding in Ubuntu**:
   - Blue highlighted words usually represent subdirectories.
   - Green indicates executable files.
   - Plain text typically denotes regular files.

- **ls -l** and **ll**:
   - Both commands provide a long listing format of directory contents, showing detailed information like permissions, ownership, size, and modification date.

- **Understanding Permissions and Ownership**:
   - "d" indicates a directory.
   - A blank space indicates a regular file.
   - The third column shows the user who owns the file.
   - The fourth column shows the group that owns the file.
   - Permissions are indicated numerically (Read = 4, Write = 2, Execute = 1).

- **ls -a**:
   - Lists all files in the directory, including hidden files (those starting with a dot).

- **mkdir**:
   - Creates a new directory.
   - `mkdir scripts/notes -p` creates the specified path, including any necessary parent directories.

- **..** (Double Dot):
   - Represents the parent directory.
   - Used to navigate up one level in the directory hierarchy.

- **cp**:
   - Copies files and directories.

- **touch**:
   - Creates new, empty files.

- **Terminal Editors**:
   - Includes `nano`, `vi`, and `vim`, which are common text editors in Linux.

- **mv**:
   - Moves or renames files and directories.
   - `mv ../dataset1 .` moves `dataset1` from one level up to the current directory.

- **rmdir**:
   - Removes directories, but only if they are empty.

- **rm -r**:
   - Removes directories and their contents recursively.
   - `rm -r ./directorydataset` removes the specified directory and all its subdirectories and files.

- **rm -f**:
   - Forces the removal of files or directories without prompting for confirmation.

<br>

## Navigating the Linux File System

- **pwd**:
   - Displays the current working directory.

- **cd**:
   - Changes the current directory to another directory.

- **ls -l or ll**:
   - Lists the contents of a directory in long format, showing detailed information.

- **ls b***:
   - Lists all files and directories starting with the letter 'b'.

- **ls -d b***:
   - Lists directories starting with 'b' without showing their contents.

- **lsblk**:
   - Lists all block devices (like hard drives and USB drives) connected to the system.

- **lsblk --scsi**:
   - Specifically lists SCSI block devices.

- **fdisk**:
   - A utility to view and manage disk partitions.
   - `sudo fdisk /dev/sda1 -l`: Lists the partitions on the `/dev/sda1` drive.

- **mount**:
   - Manages mounted filesystems.
   - Filesystems are attached to a directory tree at the mount point.
   - `mount | grep boot`: Searches for the mount point of the boot partition.

- **Disk Space Utilization Commands**:
   - **df**: Displays information about the disk space usage of mounted filesystems.
      - `df -h`: Shows the disk space usage in human-readable format (e.g., MB, GB).
   - **du**: Provides disk usage of files and directories.
      - `du -h`: Shows the disk usage in a human-readable format.
      - `du -sh * | sort -hr`: Summarizes disk usage of each item in the current directory and sorts them in human-readable format, largest first.

<br>

## Searching the Linux File System

- **find**:
   - A powerful command used to search for files and directories within the file system based on various criteria.
   - `sudo find / -name "[Bb]udget*"`: Searches the entire file system for files or directories whose names start with 'Budget' or 'budget'.
   - `sudo find / -name "[Bb]udget*" -user user1`: Narrows the search to files or directories named 'Budget' or 'budget' and owned by 'user1'.

- **Redirection Operators**:
   - `>`: Redirects output to a file or another command.
   - `2>`: Redirects standard error to a file or another command.
   - `2>/dev/null`: Redirects standard error to `/dev/null`, effectively discarding any error messages.

- **Specific Searches with find**:
   - `sudo find / -type d -name apache2`: Searches for directories named 'apache2'.
   - `sudo find / -type f -perm 0740`: Finds files with specific permissions (in this case, files where the user has read, write, and execute permissions; the group has read permissions; and others have no permissions).

- **locate**:
   - A command that uses a database of indexed files to quickly locate files.
   - Typically faster than `find` as it searches through a pre-built database rather than the file system.
   - May require installation: `sudo apt install plocate`.
   - `ls /var/lib/plocate`: Lists the contents of the directory where the `locate` database files are stored.
   - `sudo updatedb`: Updates the `locate` database to reflect the current state of the file system.
   - `locate mysql`: Searches for all files related to 'mysql'.

<br>

## Filtering Data with Linux Commands

<br>

### grep:
- **grep**: A powerful tool used for searching text data sets for lines that match a given pattern.
- **Examples**:
  - `cat cities.txt | grep -i london`: Searches for 'london' in `cities.txt`, ignoring case.
  - `grep -i london < cities.txt`: Directs the content of `cities.txt` into `grep` to search for 'london', ignoring case.
  - `grep -i london *`: Searches for 'london' in all files in the current directory, ignoring case.

<br>

### sed:
- **sed**: A stream editor used for performing basic text transformations on an input stream (a file or input from a pipeline).
- **Examples**:
  - `sed 's/London/Liverpool/' customers.txt`: Replaces the first instance of 'London' with 'Liverpool' in each line of `customers.txt`, but only in the command line output.
  - `sed 's/London/Liverpool/' customers.txt > new_customers.txt`: Performs the same substitution and writes the output to `new_customers.txt`.

<br>

### awk:
- **awk**: A powerful programming language designed for text processing and typically used for data extraction and reporting.
- **Examples**:
  - `awk '{print $2, $3}' customers.txt`: Prints the 2nd and 3rd fields (columns) from each line in `customers.txt`.
  - `awk '{print NR, $0}' customers.txt`: Prints each line in `customers.txt` with its line number.
  - `awk -F: '{print $1}' /etc/passwd`: Splits lines in `/etc/passwd` by colon (`:`) and prints the first field, typically the username.
