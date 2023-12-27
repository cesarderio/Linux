# Installing Linux

<br>

## Linux Installation Sources:

<br>

### Manual Installations:

- **ISO DVD Image**: Installing Linux from an ISO image burned to a DVD.
- **Installation Files from Local or Network Storage**: Using local or networked media to install Linux.
- **Preboot Execution Environment (PXE) Boot**: Network-based installation method that loads installation files from a server.

<br>

### Automated Installations:

- **Pre-installed Virtual Machine**: Linux pre-installed on a virtual machine image.
- **Scripted Installation**: Automated installation process using scripts.
- **PXE Boot**: Automated network boot and installation.
- **Apply OS Image**: Deployment of a pre-configured Linux OS image.
- **Cloud Template (Infrastructure as Code)**: Using cloud templates for automated deployment, often part of an Infrastructure as Code strategy.

Specific Installation Methods for Distros:
- **Ubuntu**: Utilizing an *autoinstall config file* for automated installations.
- **Red Hat Enterprise Linux (RHEL)**: Employing a *Kickstart automation file* for streamlined installation processes.

<br>

### Linux Installation Details:

- **Language and Keyboard Layout**: Setting up preferred language and keyboard configurations.
- **Installation Type (Full/Minimal)**: Choosing between a full installation or a minimal setup.
- **Third-Party Device Drivers**: Installing drivers for non-standard or specialized hardware.
- **Network Connectivity**: Configuring network settings during installation.
- **Mass Storage Configuration**: Setting up storage devices and partitions.
- **User Credentials**: Creating usernames and passwords.
- **Additional Software Packages**: Selecting extra software to install.
- **Updates**: Configuring settings for receiving system updates.
- **HWE Kernel**: Installing the Hardware Enablement (HWE) kernel for improved hardware support, especially important for third-party drivers and software.

<br>

### Local Linux Installation:
- **With or Without Scripted Files, Additional Software Packages, and Device Drivers**: Options for a customized installation.
- **Installation from Hard Disk, USB-Attached Storage**: Using local storage media for installation, which can include automated installation files.

<br>

### PXE - Preboot Execution Environment Boot Installation:

- **Enable PXE in BIOS**: Necessary step to allow network boot.
- **PXE and DHCP Integration**: PXE uses DHCP to obtain network configuration details.
- **Network Boot Process**: The device boots from its network card firmware and performs a DHCP broadcast to acquire IP configuration, even before the OS is installed.
- **Communication with PXE Server**: After network configuration, the device communicates with the PXE server.
- **Completing Linux Installation via PXE**: The installation can be manual or scripted, with the option to apply a specific Linux OS image.

<br>

## Installing a Linux Server

- **Choosing Installation Media**: Various distributions of Linux are available, each tailored for server use. The choice depends on the server's intended role and the user's preference.
    - Examples of server-focused distributions include Ubuntu Server, CentOS (now succeeded by Rocky Linux and AlmaLinux), and Debian Server.
- **Installation Process**: The installation process typically involves setting up network configurations, disk partitioning, and selecting packages relevant to the server's intended role.
- **Post-Installation Configuration**: After installation, server-specific configurations like setting up network services, firewalls, and user accounts are crucial.

<br>

## Installing a Linux Desktop

- **Selecting a Distribution**: Desktop distributions are designed for ease of use and typically come with a graphical user interface. Popular choices include Ubuntu, Fedora, and Linux Mint.
- **Installation Steps**: The process usually includes creating a bootable USB drive, partitioning the hard drive, and going through a guided setup.
- **Post-Installation**: Users can customize their desktop environment, install additional software, and configure system settings for personal use.

<br>

## Deploying a Cloud-Based Linux Server

- **Choosing a Cloud Provider**: Options include AWS, Azure, Google Cloud Platform, and other cloud services offering Linux server instances.
- **Instance Setup**: Involves selecting the server size (CPU, memory, storage), choosing the Linux distribution, and configuring network settings such as IP addresses and security groups.
- **Access and Management**: Once deployed, cloud-based Linux servers are typically managed remotely via SSH. Additional tools like Ansible, Puppet, or Chef can be used for configuration management.
- **Scalability and Maintenance**: One of the advantages of cloud-based servers is the ease of scaling resources as per demand. Regular updates and security patches are essential for maintaining server health and security.
