# Network Storage

## Storage Area Networks and Network Attached Storage

<br/>

### Storage Area Networks (SAN)

- **Definition**: A SAN is a dedicated network specifically for storage communications.
- **Purpose**: Allows storage consumers, such as Linux servers, to access shared storage over a network.
- **Types of SANs**:
  - **iSCSI SAN**: Uses standard network equipment. SCSI commands are embedded within IP packets and sent over the network. iSCSI initiators (consumers) connect to iSCSI targets (storage providers) typically listening on TCP port 3260.
  - **Fibre Channel (FC) SAN**: A high-speed SAN designed for enterprise use with specialized equipment like host bus adapters (HBAs) and Fibre Channel switches. More expensive than iSCSI, it offers redundancy and high performance.

<br/>

### iSCSI SAN Configuration

- **Components**:
  - **iSCSI Initiators**: Can be software agents in the OS or specialized controller cards in the server.
  - **iSCSI Targets**: Network storage units that provide storage.
- **Network Setup**: Typically set up with a dedicated VLAN for isolated data transfer.
- **Storage Management**: To the Linux server, iSCSI storage appears like local storage, which can be partitioned and managed accordingly.

<br/>

### Fibre Channel (FC) SAN

- **Characteristics**: Uses specialized equipment for high-speed, secure, and reliable storage networking.
- **Redundancy**: Multiple paths to storage for redundancy, mitigating the risk of a single point of failure.
- **Storage Arrays**: Often include backup units for data protection.
- **Security Considerations**: Include data encryption at rest, file access auditing, and physical security.

<br/>

### Network Attached Storage (NAS)

- **Functionality**: A NAS device is a specialized storage appliance for sharing files over a network.
- **Protocols**: Accessible using file sharing protocols like SMB and NFS.
- **Disk Management**: Supports JBOD (Just a Bunch of Disks) and various RAID configurations.
- **Use Cases**: Ideal for centralized file sharing and storage in a network environment.

<br/>

### Summary

- SANs and NAS provide flexible, centralized storage solutions for Linux environments.
- SANs, especially iSCSI and FC, offer dedicated, high-performance storage networking.
- NAS devices facilitate easy file sharing and storage expansion.

<br/>

### Key Points for Linux Configuration

- **iSCSI Initiators**: Linux servers can be configured as iSCSI initiators to connect to iSCSI SANs.
- **FC SAN Connection**: Requires specialized hardware (HBAs) and configuration for connectivity.
- **NAS Integration**: Linux can easily connect to NAS devices via standard network protocols.

<br/>

## Configuring a Linux-based iSCSI Initiator

<br/>

### Introduction to iSCSI in Linux

- **Objective**: Connect a Linux host to network storage using iSCSI (Internet Small Computer Systems Interface).
- **Setup**: Utilize a Windows Server as the iSCSI target and a Linux machine as the iSCSI initiator.

<br/>

### Setting Up the iSCSI Target on Windows Server

1. **Install iSCSI Support**:
   - Access Server Manager and add the iSCSI Target Server role under File and Storage Services.

2. **Create an iSCSI Virtual Disk**:
   - Use the Server Manager to create a new iSCSI virtual disk on an available drive.
   - Example: Name the disk `iSCSI_Vdisk1` and set its size to 9.91 GB.

3. **Configure iSCSI Target**:
   - Create a new target (e.g., `LinuxHosts`) and specify which initiators (IP addresses) are allowed to connect.
   - Note the IQN (iSCSI Qualified Name) of the target for later use.

<br/>

### Configuring the Linux iSCSI Initiator

1. **Discover iSCSI Target**:
   - Run `sudo iscsiadm --mode discovery --type sendtargets --portal [Windows Host IP]` to discover the iSCSI target on the Linux host.

2. **Connect to iSCSI Target**:
   - Use `sudo iscsiadm --mode node --targetname [IQN] --portal [Windows Host IP] --login` to initiate a connection to the iSCSI target.

3. **Verify Connection**:
   - Confirm the connection using `lsblk --scsi | grep iscsi` and `sudo fdisk -l`.
   - The iSCSI disk should appear as a local device (e.g., `/dev/sde`).

<br/>

### Setting Up the iSCSI Disk on Linux

1. **Partition the iSCSI Disk**:
   - Use `sudo fdisk /dev/sde` to create a new partition on the iSCSI disk.

2. **Format the Partition**:
   - Format the new partition with a filesystem (e.g., ext4) using `sudo mkfs -t ext4 /dev/sde1`.

3. **Create Mount Point and Mount the Disk**:
   - Create a directory for mounting (e.g., `sudo mkdir /iscsi`).
   - Mount the iSCSI disk to the created directory: `sudo mount /dev/sde1 /iscsi`.

4. **Verify Mount**:
   - Use `sudo mount | grep iscsi` to ensure the disk is successfully mounted.

<br/>

### Summary

- **iSCSI in Linux**: Enables a Linux host to use network storage as if it were local, enhancing storage flexibility and capacity.
- **Configuration Process**: Involves setting up an iSCSI target on a Windows Server, discovering and connecting to it from a Linux host, and then partitioning, formatting, and mounting the iSCSI disk on Linux.
