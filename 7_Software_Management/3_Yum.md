# Managing Linux Repositories and Updates with Yum

<br>

## Introduction

This guide focuses on managing Linux repositories and performing updates using the `yum` command line tool, which is integral for RPM (Red Hat Package Manager) package management. We'll use a Red Hat Enterprise Linux host for this demonstration.

<br>

## Getting Started with `yum`

1. **Exploring Yum Commands**:
   - Command: `yum -help`
   - Reveals various parameters for managing packages and repositories.

2. **Listing Repositories**:
   - Command: `sudo yum repolist`
   - Shows the repositories checked for installing and updating software.

3. **Checking Repository Configuration Files**:
   - Path: `/etc/yum.repos.d`
   - Example: Viewing `redhat.repo` with `cat /etc/yum.repos.d/redhat.repo`.

<br>

## Listing Installed Packages

1. **Viewing Installed Packages**:
   - Command: `sudo yum list installed | more`
   - Shows names and versions of installed packages.

2. **Filtering for Specific Packages**:
   - Example: Filtering for Python packages with `sudo yum list installed | grep python`.

<br>

## Keeping Repositories Updated

1. **Updating Repository Indexes**:
   - Command: `sudo yum check-update`
   - Ensures the repository listing and software package indexes are current.

2. **Applying Updates**:
   - Command: `sudo yum update`
   - Downloads and installs updates for installed packages.

<br>

## Installing New Software

1. **Searching for Packages**:
   - Example: Searching for Docker with `sudo yum search docker`.

2. **Getting Package Details**:
   - Command: `sudo yum info docker`
   - Provides details like name, version, size, and release string.

3. **Installing a Package**:
   - Command: `sudo yum -y install docker`
   - Installs Docker and starts the service.

<br>

## Managing Individual Packages

1. **Checking Package Status and Starting Services**:
   - Commands: `sudo service docker status` and `sudo service docker start`.

2. **Updating Specific Packages**:
   - Command: `sudo yum update docker`
   - Updates the named package, if updates are available.

3. **Removing Packages**:
   - Command: `sudo yum -y remove docker`
   - Uninstalls Docker and confirms its removal.

<br>

## Additional RPM Management

1. **Using RPM Command Line Tool**:
   - Install: `rpm -i [package]`
   - Erase: `rpm -e [package]`
   - For more options: View the manual page with `man rpm`.

<br>

## Conclusion

This guide covers the essentials of managing Linux repositories and performing software updates using `yum` on Red Hat Linux systems. Understanding these processes is crucial for effective software management and maintenance in RPM-based Linux environments.
