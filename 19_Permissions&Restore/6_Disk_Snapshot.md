# Configuring Virtual Machine Disk Snapshots in Microsoft Azure

<br>

## **Overview**

- **Purpose**: Reverting to earlier points in time for virtual machines (VMs) in cloud environments.
- **Platform**: Microsoft Azure (applicable to other cloud platforms like Google Cloud Platform or Amazon Web Services).

<br>

### **Steps to Configure Disk Snapshots**

1. **Access Virtual Machine**:
   - Go to Azure portal.
   - Navigate to "Virtual machines".
   - Select the desired virtual machine (e.g., Ubuntu2).

2. **Navigate to Disks Section**:
   - Inside VM properties, click on "Disks".
   - View Operating System (OS) disk and additional data disks.

3. **Create Snapshot**:
   - Click on the OS disk link.
   - Select "Create snapshot".
   - Deploy snapshot into a resource group and name it (e.g., Ubuntu2_OSDisk_Snapshot).
   - Choose between Full or Incremental snapshot.
   - Proceed through encryption and public access settings.
   - Validate and create the snapshot.

<br>

### **Using the Snapshot**

- **Viewing Snapshots**: Go to "All resources" and filter by snapshots.
- **Applying the Snapshot**:
  - Go back to VM Disks section.
  - Use "Swap OS Disk" but note snapshots don’t appear directly in the dropdown list.

<br>

### **Creating a Managed Disk from Snapshot**

1. **Create New Disk**:
   - From the home page, create a resource.
   - Search "managed".
   - Select "Microsoft Managed Disks" and create.
   - For source type, choose the snapshot.
   - Name the new disk (e.g., Ubuntu2_NewOSDiskTest) and select the snapshot as the source.
   - Review and create the new disk.

2. **Swap the OS Disk**:
   - Return to VM and swap the OS disk with the newly created disk from the snapshot.

3. **Create New VM from Disk**:
   - Go to "All resources".
   - Filter for the new disk (Ubuntu2_NewOSDiskTest).
   - Create a new VM from this disk.

<br>

## Key Considerations

- **Purpose of Snapshots**: Essential for reverting VMs to a previous state, especially useful in testing and disaster recovery scenarios.
- **Full vs Incremental Snapshots**: Full snapshots are complete copies, while Incremental snapshots save storage by only capturing changes since the last snapshot.
- **Managed Disks**: Facilitates creating new VMs or swapping disks in existing VMs from snapshots.

<br>

## Conclusion

Understanding and efficiently using VM disk snapshots in Microsoft Azure (or other cloud platforms) provides a robust mechanism for managing VM states, offering flexibility and security in handling various scenarios like testing configurations or recovering from issues.
