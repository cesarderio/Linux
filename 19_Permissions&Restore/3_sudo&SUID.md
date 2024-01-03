# Managing Sudo and Special User ID (SUID) in Linux

<br>

## **Understanding Sudo for Elevated Privileges**

- **Basic Usage**: `sudo` is used to run commands with elevated privileges.
- **Checking Current User**: `whoami` indicates the current logged-in user.
- **Example**: Using `sudo` to run `fdisk -l` which requires elevated privileges.
- **Editing Sudoers File**:
  - Accessed via `sudo visudo`.
  - Configures which users can run specific commands.
  - Root user example: `root ALL=(ALL:ALL) ALL`.

<br>

### **Resetting Root Password with Sudo**

- **Command**: `sudo passwd root` allows setting or updating the root password.
- **Applicability**: Useful for inherited systems where root password is unknown.

<br>

### **Special User ID Bit (SUID)**

- **Purpose**: Allows a file to be executed with the permissions of the file's owner.
- **C Program Example**:
  - Created a file `test.c`.
  - Contains a script `test.sh` to run `fdisk -l`.

<br>

### **Demonstrating SUID with C Program**

- **C Program Contents**: Compiles `test.sh` into a C program.
- **Compiling the Program**:
  - Command: `gcc test.c -o test.bin`.
  - Requires GCC (GNU Compiler Collection) installed.

<br>

### **Setting SUID on Binary File**

- **Changing Owner to Root**: `sudo chown root test.bin`.
- **Setting SUID**: `sudo chmod 4755 test.bin`.
  - `4` activates SUID bit.
  - `755` sets permissions (read, write, execute for owner, read and execute for others).

<br>

### **Testing SUID**

- **Running Script vs. Binary**:
  - Script (`test.sh`): Fails with "Permission Denied" despite SUID due to modern security restrictions.
  - Binary (`test.bin`): Executes successfully, running with root privileges.

<br>

### **Key Takeaways**

- **SUID on Scripts**: Modern Linux distributions do not allow scripts to run with SUID for security reasons.
- **SUID on Binaries**: Binaries can effectively utilize SUID to execute with the permissions of the file owner.
