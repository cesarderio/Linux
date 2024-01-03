# Monitoring Memory Performance in Linux

<br>

## Exploring Memory Metrics

<br>

### Accessing Memory Information

- **/proc Directory**: Contains subdirectories for each process ID and files with system statistics.
- **meminfo File**: Provides detailed memory statistics, accessible with `cat meminfo | more`.

<br>

### Commonly Used Commands

- **free Command**: Offers a simpler view of total and available memory.
- **top Command**: Displays top resource-consuming processes, updating in real-time.
- **ps Command**: Shows all running processes and their memory usage, using `ps -aux | more`.
- **htop Command**: An interactive version of `top`, with a focus on memory usage.
- **ulimit Command**: Limits memory available to users, configurable for each user.

<br>

### Memory Monitoring in Virtual Environments

- **Microsoft Azure Portal**: Demonstrates how to monitor memory performance of Linux virtual machines in a cloud environment.

<br>

## Key Points

- **Real-Time Monitoring**: Essential for identifying memory-intensive processes.
- **%MEM Column**: Indicates the memory usage of each process.
- **Environment Settings**: Include temperature control to prevent overheating and throttling.
- **Virtual Machine Resource Adjustment**: Allows resizing VM settings to meet workload demands.
- **Documentation and Baselines**: Crucial for understanding normal performance levels and changes over time.
