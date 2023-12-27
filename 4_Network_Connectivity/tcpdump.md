# Capturing and Analyzing Network Traffic Using tcpdump

<br>

## Introduction

- **Objective**: Learn how to use tcpdump to capture and analyze network traffic on Linux.


<br>

## Using tcpdump for Traffic Analysis

1. **Initial Setup**:
   - Identify active network interfaces using the `ip a` command.
   - Example interface: `ens33` with IP address 192.168.2.41.

2. **Basic Traffic Capture**:
   - Command: `sudo tcpdump -i ens33 -v` to start capturing traffic on interface `ens33` with verbose output.
   - Capturing to File: Use `-w` option to write output to a pcap file, e.g., `sudo tcpdump -i ens33 -v -w packetcapture1.pcap`.

3. **Reading Captured Data**:
   - Command: `sudo tcpdump -r packetcapture1.pcap` to read and analyze the pcap file.
   - Observation: Analyze SSH traffic, client ports, and other details.

4. **Applying Capture Filters**:
   - Filter by Host: `sudo tcpdump -i ens33 host 192.168.2.11 -v` captures traffic related to a specific IP address.
   - Writing Filtered Output: Capture specific host traffic to a file, e.g., `sudo tcpdump -i ens33 host 192.168.2.11 -v -w hostfilter.pcap`.

5. **Advanced Filtering**:
   - Destination Filtering: Use `dst` keyword to capture traffic destined to a specific host, e.g., `sudo tcpdump -i ens33 dst 192.168.2.11 -v -w hostfilter.pcap`.
   - Protocol Filtering: Capture specific protocol traffic like ICMP, e.g., `sudo tcpdump -i ens33 -v -n icmp`.

6. **Port-Specific Capture**:
   - Command: `sudo tcpdump -i ens33 -v port 22` to capture only traffic on port 22 (SSH).

7. **Learning More**:
   - Explore additional options and filters by consulting the manual page: `man tcpdump`.

<br>

## Practical Applications

- **Network Troubleshooting**: Identify and diagnose network communication issues.
- **Traffic Monitoring**: Observe network traffic patterns and detect anomalies.
- **Security Analysis**: Inspect network traffic for security assessments.

<br>

## Summary

- **tcpdump Proficiency**: Mastery of tcpdump is crucial for network analysis in Linux.
- **Filtering Techniques**: Employing various filtering options to focus on specific network traffic components.
