# Configuring User and Group File System Quota Limits in Linux

<br>

## **Introduction**

- **Purpose**: Imposing restrictions on disk space usage.
- **Tools**: Quota management tools for disk capacity restrictions.

<br>

### **Initial Setup**

1. **Update Package List**:
   - Command: `sudo apt update`.
2. **Install Quota Tools**:
   - Command: `sudo apt install quota`.
3. **Check Quota Version**:
   - Command: `quota --version`.

<br>

### **Configuring Quotas**

1. **Enable Quotas in File System**:
   - Edit `/etc/fstab` file.
   - Add `usrquota, grpquota` options for desired file systems.
2. **Remount with Quota Options**:
   - Command: `sudo mount -o remount /`.
   - Confirm user and group quotas are active.
3. **Perform Quota Check**:
   - Command: `sudo quotacheck -ugm /`.

<br>

### **Setting Individual User Quotas**

1. **Identify User**:
   - Example: User `jgold`.
   - Command: `sudo tail /etc/passwd`.
2. **Edit User Quota**:
   - Command: `sudo edquota -u jgold`.
   - Set soft and hard limits (e.g., 409600 and 512000 blocks).

<br>

### **Activating Quotas**

- Command: `sudo quotaon -uv /home`.
- Note: Applies if `/home` is a separate mount point.

<br>

### **Viewing Quota Reports**

- Command: `sudo repquota -au`.
- Provides a report of used storage blocks and configured limits.

<br>

### **Setting Group Quotas**

1. **Create a New Group**:
   - Command: `sudo groupadd usergroup1`.
   - Command: `sudo tail /etc/group`.
2. **Edit Group Quota**:
   - Command: `sudo edquota -g usergroup1`.
   - Configure limits for the group.

<br>

### **Grace Periods**

- Not specified in this demo.
- Applies to soft limits allowing temporary exceedance.

<br>

## Key Points

- **Quota Management**: Essential for controlling disk usage on a per-user and per-group basis.
- **File System Configuration**: Modifying `/etc/fstab` to enable quotas and remounting the file system.
- **User and Group Limits**: Setting soft and hard limits for both users and groups to manage disk space efficiently.
- **Monitoring Usage**: Using `repquota` to generate reports on disk usage and quota limits.
- **Flexibility**: Quotas provide a flexible way to manage disk resources, especially in multi-user environments.
