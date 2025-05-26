# Wireshark Analysis with Nmap Scan

## 🔧 Command Used for Packet Capture

`nmap -sS -sV -O 192.168.1.0/24`

##### 🔍 Explanation:
 
 This command performs a combined scan, including:

- -sS: TCP SYN scan to detect open ports

- -sV: Version detection of running services

- -O: OS detection (based on TCP/IP fingerprinting)

> While this scan ran, I captured the network traffic using Wireshark to analyze what exactly Nmap was sending and receiving.


 ## 🧠 Wireshark Filters Used
I used the following display filters:

 - tcp.flags.syn == 1 && tcp.flags.ack == 0	Shows SYN packets sent by Nmap (port discovery)
 - tcp.flags.syn == 1 && tcp.flags.ack == 1	Shows SYN-ACK replies from open ports
 - tcp.flags.reset == 1	Shows RST packets indicating closed ports

 
 #### 📸 Screenshots

 - [SYN Packets Sent](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/wireshark_syn_packets.png)

 - [SYN-ACK Received](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/wireshark_syn_ack.png)

 - [RST Packets](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/wireshark_rst_packets.png)


## Summary

By running the Nmap scan and capturing the network traffic with Wireshark at the same time, I got to actually **see what's happening behind the scenes**:

- I could **watch Nmap send SYN packets** to different devices to check if ports are open.
- I saw how **devices replied differently** depending on whether the port was open or closed.
 -I also noticed **how Nmap tries to detect the OS and service versions** based on the way those devices respond.

-----

