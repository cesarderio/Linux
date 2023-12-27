# LVM - Logical Volume Management

## Understanding Logical Volume Management (LVM) in Linux

<br/>

### What is LVM?

- **Definition**: LVM stands for Logical Volume Management.
- **Functionality**: Allows grouping together storage media (physical or virtual) into a single logical unit.
- **Purpose**: Provides a flexible way of managing storage space across multiple disks.

<br/>

### Key Concepts in LVM

1. **Physical Volume (PV)**:
   - Represents a physical or logical storage device.
   - Can be a physical disk or a logical disk in a virtual machine.

2. **Volume Group (VG)**:
   - A collection of physical volumes pooled together.
   - Allows the combination of multiple physical volumes into a larger virtual storage unit.

3. **Logical Volume (LV)**:
   - A portion of a volume group that is presented to the operating system as a logical volume.
   - Acts similarly to a disk partition from the OS perspective.

<br/>

### LVM vs RAID

- **Differences from RAID**:
  - LVM does not inherently provide data redundancy or parity like some RAID levels (e.g., RAID 5).
  - LVM is primarily focused on flexible disk space management across multiple devices.

<br/>

### Configuring LVM in Linux

1. **Identifying Disks for LVM**:
   - Use `lvmdiskscan` to scan for available disks.
   - Mark the desired disks for LVM use.

2. **Creating Physical Volumes (PVs)**:
   - Use `pvcreate` to initialize physical volumes for LVM.
   - Example: `sudo pvcreate /dev/sdb /dev/sdc /dev/sdd`.

3. **Creating a Volume Group (VG)**:
   - Combine PVs into a VG using `vgcreate`.
   - Example: `sudo vgcreate VolGroup1 /dev/sdb /dev/sdc /dev/sdd`.

4. **Creating Logical Volumes (LVs)**:
   - Use `lvcreate` to create logical volumes within a VG.
   - Example: `sudo lvcreate -L 50G -n projects VolGroup1`.

5. **Formatting and Mounting the LV**:
   - Format the LV with a filesystem (e.g., ext4).
   - Mount the LV to a directory for use.
   - Example: `sudo mkfs -t ext4 /dev/VolGroup1/projects` and `sudo mount /dev/VolGroup1/projects /projects`.

6. **Making Persistent Mounts**:
   - Edit `/etc/fstab` to ensure the LV mounts automatically on boot.

<br/>

### Advantages of LVM

- **Flexibility**: Easily resize and manage storage without being constrained by physical disk sizes.
- **Efficiency**: Optimize storage utilization by allocating space based on actual usage and demand.
- **Convenience**: Manage storage with logical names and resize volumes without unmounting or affecting uptime.


<br/>

## Configuring Logical Volume Management (LVM) in Linux

<br/>

### Introduction to LVM

- **Purpose**: LVM allows for flexible management of physical storage space in Linux by grouping multiple storage devices into a single logical unit.
- **Components**:
  - **Physical Volumes (PVs)**: Individual storage devices.
  - **Volume Group (VG)**: A pool of physical volumes.
  - **Logical Volumes (LVs)**: Segments of a volume group that are presented to the OS as logical units.

<br/>

### Step-by-Step Configuration Process

1. **Identifying Suitable Storage Devices**:
   - Run `sudo lvmdiskscan` to list available storage devices.
   - Focus on specific devices (e.g., `/dev/sdb`, `/dev/sdc`, `/dev/sdd`) for LVM use.

2. **Creating Physical Volumes**:
   - Use `sudo pvcreate` to initialize physical volumes for LVM.
   - Example: `sudo pvcreate /dev/sdb /dev/sdc /dev/sdd`.

3. **Verifying Physical Volume Creation**:
   - Run `sudo pvs` to list and verify the created physical volumes.

4. **Creating a Volume Group**:
   - Combine physical volumes into a volume group with `sudo vgcreate`.
   - Example: `sudo vgcreate VolGroup1 /dev/sdb /dev/sdc /dev/sdd`.

5. **Verifying Volume Group Creation**:
   - Use `sudo vgs` to confirm the creation and size of the volume group.

6. **Creating a Logical Volume**:
   - Use `sudo lvcreate` to create a logical volume within a volume group.
   - Specify size and name for the logical volume.
   - Example: `sudo lvcreate -L 50G -n projects VolGroup1`.

7. **Formatting the Logical Volume**:
   - Format the new logical volume with a filesystem (e.g., ext4).
   - Example: `sudo mkfs -t ext4 /dev/mapper/VolGroup1-projects`.

8. **Mounting the Logical Volume**:
   - Create a mount point and mount the logical volume.
   - Example: `sudo mkdir /projects && sudo mount /dev/VolGroup1/projects /projects`.

9. **Making the Mount Persistent**:
   - Edit `/etc/fstab` to ensure the logical volume is mounted automatically at boot.
   - Add an entry for the logical volume specifying the mount point, filesystem type, and other mount options.

<br/>

### Key Takeaways

- **Flexibility**: LVM allows for dynamic resizing and management of storage.
- **Efficiency**: Multiple physical disks can be managed as a single unit, simplifying storage administration.
- **Practical Use**: Ideal for situations where storage needs may change over time, allowing for easy expansion or reduction of storage space.

<br/>

### Additional Tips

- **Space Allocation**: Leave some free space in the volume group for LVM to function correctly and for future expansion.
- **Persistent Mounts**: Properly configuring `/etc/fstab` is crucial for ensuring that the logical volume remains accessible after system reboots.
