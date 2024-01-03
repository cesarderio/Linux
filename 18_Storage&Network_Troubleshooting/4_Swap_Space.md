# Managing Linux Swap Space

<br>

## Understanding Swap Space

- **Function**: Swap space is used when RAM is exhausted, allowing the OS to swap out least frequently accessed memory blocks to disk.
- **Configuration**: It can be configured as a file or as a dedicated disk partition.

<br>

## Checking Swap Space

- **Free Command**: Use `free -m` to check current swap space. In your example, there was initially no swap space configured.

<br>

## Adjusting Virtual Machine Resources

- **VMware Workstation**: Modify virtual hardware settings, such as increasing RAM.
- **Microsoft Azure Portal**: Resize virtual machines to include more RAM as needed.

<br>

## Setting Up Swap Space

- **Identifying Disk**: Use `sudo fdisk -l` to identify available disks and partitions.
- **Creating Swap Partition**: Use `sudo fdisk /dev/sdd` (for example) to create a new partition on the chosen disk.
- **Formatting Swap Space**: Use `sudo mkswap /dev/sdd1` to format the new partition as swap space.
- **Enabling Swap**: Use `sudo swapon -v /dev/sdd1` to enable the newly created swap space.
- **Verification**: Run `free -m` again to verify that swap space is recognized and available for use.

<br>

## Importance of Swap Space

- **Performance**: Swap space can mitigate memory constraints during peak workloads.
- **Cost-Effective Solution**: It's a potential alternative to adding physical RAM, especially in virtualized or cloud environments.
