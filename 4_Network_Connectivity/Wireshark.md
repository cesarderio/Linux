# Capturing and Analyzing Network Traffic Using Wireshark

<br>

## Introduction

- **Objective**: Master the use of Wireshark for capturing and analyzing network traffic.


<br>

## Steps for Using Wireshark

1. **Installation and Setup**:
   - Download and install Wireshark from wireshark.org.
   - Open Wireshark and identify available network adapters (e.g., Wi-Fi, Ethernet).

2. **Starting a Capture Session**:
   - Double-click on a network adapter to start capturing traffic.
   - Capture all network traffic visible to your machine.

3. **Analyzing Captured Packets**:
   - Stop the capture by clicking the Stop button.
   - Select a packet to view its details, including Ethernet II header (Layer 2) and IP header (Layer 3).
   - Explore packet headers for MAC addresses, TTL values, Source/Destination IPs, and port numbers.

4. **Applying Display Filters**:
   - Use display filters to focus on specific traffic (e.g., `tcp.port == 443` for HTTPS traffic).
   - Experiment with different filters like protocol names or port numbers.

5. **Saving and Opening Capture Files**:
   - Save your packet capture for later analysis through File > Save.
   - Open existing capture files, including those captured with tcpdump.

6. **Auditing Network Traffic**:
   - Examine packet contents for sensitive information like plaintext usernames and passwords.
   - Be aware of unencrypted protocols (e.g., FTP, Telnet) that transmit credentials in clear text.

7. **Following TCP Streams**:
   - Select a TCP packet and use Analyze > Follow > TCP Stream to view the entire conversation.
   - Inspect details like login credentials and issued commands in a more consolidated view.

8. **Best Practices**:
   - Prefer encrypted protocols like SSH over Telnet for secure communication.
   - Regularly audit your network to identify and rectify security vulnerabilities.

<br>

## Walkthrough for Analyzing Network Traffic

- **Start Wireshark**: Launch the application and select the network adapter to monitor.
- **Capture Traffic**: Initiate packet capturing to start recording network activity.
- **Inspect Packets**: Browse through captured packets, examining protocol layers and headers.
- **Apply Filters**: Utilize display filters (e.g., `ip.addr == [IP address]`) to isolate specific traffic.
- **Follow Streams**: Use the 'Follow TCP Stream' feature to visualize entire sessions, aiding in understanding the flow of communication.
- **Save Analysis**: Save the captured session for future reference or detailed analysis.

<br>

## Practical Applications

- **Network Troubleshooting**: Identify and resolve network issues by analyzing traffic patterns and anomalies.
- **Security Monitoring**: Detect unauthorized access or insecure protocols in network traffic.
- **Performance Analysis**: Assess network performance by evaluating traffic flow and protocol efficiency.

<br>

## Summary

- **Wireshark Mastery**: Developing proficiency in Wireshark is essential for network technicians to capture and analyze network traffic effectively.
- **Versatility of Tools**: Leverage both Wireshark and tcpdump for comprehensive network analysis across different platforms.
