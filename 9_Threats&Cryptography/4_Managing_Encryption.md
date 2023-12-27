# File System Encryption in Linux

<br>

## Introduction

In this demonstration, we explore how to encrypt individual files and entire disk partitions on a Linux host, enhancing the confidentiality aspect of the CIA security triad.

<br>

## Encrypting Individual Files

<br>

### Installation of Encryption Tool

1. **Install GnuPG**:
   - Command: `sudo apt install gnupg2`
   - GnuPG (GNU Privacy Guard) is used for file encryption.

<br>

### Encrypting a File

1. **Verify Installation**:
   - Command: `gpg2 --version`
   - Confirms the installation and shows supported encryption and hashing algorithms.

2. **File Encryption**:
   - Encrypt a file using symmetric encryption.
   - Command: `gpg --symmetric ./Project_A.txt`
   - Enter a passphrase for encryption.

3. **Confirm Encryption**:
   - Original file `Project_A.txt` remains alongside the encrypted `Project_A.txt.gpg`.
   - Optionally, remove the original file for security.

<br>

### Decrypting a File

1. **File Decryption**:
   - Command: `gpg --output Project_A.txt --decrypt Project_A.txt.gpg`
   - Restores the original file content.

## Encrypting Disk Partitions

<br>

### Preparing the Partition

1. **List Block Devices**:
   - Command: `sudo lsblk --scsi`
   - Identify the device for encryption (e.g., `/dev/sde`).

2. **Partitioning the Device**:
   - Command: `sudo fdisk /dev/sde`
   - Create a new primary partition.

<br>

### Installing Cryptsetup

1. **Install Cryptsetup**:
   - Command: `sudo apt install cryptsetup`
   - Cryptsetup is used for disk partition encryption.

2. **Format Partition with LUKS**:
   - Command: `sudo cryptsetup luksFormat /dev/sde`
   - LUKS (Linux Unified Key Setup) is a disk encryption specification.
   - Set a passphrase for the encrypted partition.

<br>

### Mounting the Encrypted Partition

1. **Unlock Partition**:
   - Command: `sudo cryptsetup luksOpen /dev/sde cryptpart`
   - Unlocks the partition for use.

2. **Create Filesystem and Mount**:
   - Command: `sudo mkfs -t ext4 /dev/mapper/cryptpart`
   - Format the unlocked partition with the ext4 filesystem.
   - Command: `sudo mkdir /vault` and `sudo mount /dev/mapper/cryptpart /vault`
   - Mount the encrypted partition to a directory (e.g., `/vault`).

<br>

### Verifying the Mount

1. **Check Mount**:
   - Command: `sudo mount | grep vault`
   - Confirms that the encrypted partition is mounted.

<br>

## Conclusion

Encrypting files and disk partitions in Linux is a critical step towards securing data. For individual files, GnuPG provides a straightforward method for encryption and decryption. For disk partitions, Cryptsetup with LUKS offers a robust solution for securing data at rest. Once mounted, the encrypted partition behaves like a normal filesystem, ensuring that all files created or stored there are automatically encrypted.
