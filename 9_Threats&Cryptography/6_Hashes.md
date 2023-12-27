# File System Hashing in Linux

<br>

## Introduction

This guide explores generating file system hashes in Linux, a crucial process for detecting file changes due to corruption or unauthorized modifications.

<br>

## Basics of File Hashing

<br>

### Concept

- Hashing is a one-way process using algorithms to create a fixed-length hash or message digest from data.
- No keys are involved, unlike encryption, making hashing a unique process.

<br>

### Purpose

- Hashing ensures file integrity by detecting alterations in files.

<br>

## Generating Hashes in Linux

1. **Checking File Contents**:
   - Command: `cat Project_A.txt`
   - Displays the file's content for reference.

2. **Using Different Hash Algorithms**:
   - MD5: `sudo md5sum Project_A.txt`
   - SHA-256: `sudo sha256sum Project_A.txt`
   - Each algorithm generates a unique hash for the same file.

3. **Detecting File Changes**:
   - Modify `Project_A.txt` (e.g., add new text).
   - Regenerate the hash with `sha256sum`.
   - The new hash will differ from the original, indicating a change.

<br>

## User Password Hashing

- Linux stores user password hashes in the `/etc/shadow` file.
- Example: `sudo tail /etc/shadow`
- These hashes are one-way, ensuring security and integrity.

<br>

## Salting in Hashing

- Salting adds random data during the hashing process, enhancing security.
- Prevents the effectiveness of rainbow tables (precomputed hash lists).

<br>

## Scripting for Hashing

1. **Creating a Hash Script**:
   - `nano hashscript.sh`
   - Script generates hashes for a file (`file1.txt`) and appends to `file_hash_history.txt`.

2. **Running the Script**:
   - Execute: `./hashscript.sh`
   - Adds a new hash entry to `file_hash_history.txt`.

3. **Tracking File Changes**:
   - Modify `file1.txt`.
   - Rerun `hashscript.sh`.
   - Compare hashes in `file_hash_history.txt` to detect changes.

<br>

## Conclusion

Hashing is an essential tool in Linux for ensuring file integrity. By generating and comparing hashes, Linux administrators can detect file corruption or unauthorized changes. Whether it’s for individual files or user passwords, hashing serves as a reliable method to maintain data integrity. This process, particularly when automated through scripting, becomes a powerful component of a Linux system’s security framework.
