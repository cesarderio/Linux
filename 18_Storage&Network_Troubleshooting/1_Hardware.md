# Troubleshooting Storage and Network Hardware in Linux

<br>

## Storage Hardware

<br>

### Types of Storage

- **Local Storage**: Internal HDDs, SSDs, or external USB devices.
- **Network Storage**: NAS (using file-sharing protocols like SMB or NFS) and SAN (block-level storage such as iSCSI or Fiber Channel).

<br>

### Common Issues

- Incompatibility with certain hardware.
- USB device recognition problems.
- Ensuring up-to-date documentation for storage configurations.

<br>

## Network Hardware

<br>

### Components

- Physical and virtual Network Interface Cards (NICs).
- NIC bonding for aggregated bandwidth or fault tolerance.
- Compatibility issues with Wi-Fi cards, especially for security tasks requiring packet injection.

<br>

### Specialized Devices

- Hardware Security Modules (HSMs) for cryptographic functions.
- Cloud-based HSM services.

<br>

### Compatibility and Certification

- Ensuring hardware is certified for specific Linux distributions (e.g., Ubuntu Certified Hardware).

<br>

## Tools and Commands for Troubleshooting

<br>

### Storage-Related Commands

- `mount`/`umount`: Mounting and unmounting file systems.
- `lsblk`, `lsscsi`: Listing block and SCSI devices.
- `fdisk`, `partprobe`: Managing disk partitions and updating the kernel about partition changes.
- `fsck`: Checking and repairing file system corruption.

<br>

### Network-Related Commands

- `ip a`: Displaying IP addresses.
- `ping`: Testing connectivity to remote devices.
- `traceroute` (`tracert`): Displaying the route packets take to a network host.
- `ifconfig` (older distributions): Configuring network interfaces.

<br>

### Advanced Monitoring

- Viewing `/proc/net/dev` for detailed network device statistics (e.g., bytes received/sent, errors, collisions).
