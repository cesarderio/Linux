# Mastering Common Linux Networking Commands

<br>

## Introduction

- **Objective**: To familiarize with essential Linux networking commands for effective network configuration and troubleshooting.


<br>

## Overview of Networking Commands

1. **Network Interfaces Overview**:
   - Description: Linux hosts can have multiple network interfaces like `eth0`, `wlan0`, and `lo` (local loopback).
   - GUI Management: Network settings can also be managed via a graphical user interface, as shown in Ubuntu Desktop Network Settings.

2. **Essential Networking Commands**:
   - `ifconfig`: An older command for managing network interfaces. Used for listing, bringing interfaces up or down, and assigning IP addresses.
   - `ip`: Modern replacement for `ifconfig`. Displays IPv4 or IPv6 addressing information, manages network interfaces and settings.
   - `hostname`: Displays the local machine's name.
   - `arp`: Manages the ARP cache, mapping IP addresses to MAC addresses.
   - `route`: Views and manages the IP routing table.
   - `traceroute`: Shows the path traffic takes to reach a destination.
   - `dig` and `nslookup`: Tools for DNS name resolution. `nslookup` has an interactive mode.
   - `curl` and `wget`: Commands for transferring data over network protocols like FTP and HTTP.
   - `netstat`: Monitors network connections and listening sockets.
   - `nc` (netcat): Transfers data over TCP or UDP connections.

<br>

## Demonstrations

- **Command Line Interface Usage**:
   - Usage of commands like `ifconfig`, `ip`, `hostname`, and others to manage and troubleshoot network configurations.
   - Emphasis on the transition from older commands like `ifconfig` to modern equivalents like `ip`.

<br>

## Practical Applications

- **Network Configuration**: Setting up and managing network interfaces, IP addresses, and routing.
- **Troubleshooting**: Diagnosing network connectivity and performance issues.
- **Data Transfer**: Utilizing tools for efficient data transfer and network communication.

<br>

## Summary

- **Key Commands**: Mastery of a range of commands is critical for effective network management in Linux environments.
- **Modern Practices**: Emphasis on newer, more prevalent commands like `ip` over older ones like `ifconfig`.
