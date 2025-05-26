# 🔐 Task 1: Network Scanning & Traffic Analysis

## 🚀 Objective

To discover devices on the local network, identify open ports, analyze their services, and inspect packet-level data using Nmap and Wireshark.

---

## 🛠 Tools Used

- **Nmap**: For network scanning and service detection
- **Wireshark**: For monitoring and analyzing network packets
- **xsltproc**: To convert XML scan results to HTML format
- **ifconfig**: To find the host's IP address

---

## 📡 Network Setup

- **Host IP (found using `ifconfig`)**: `192.168.1.6`
- **Target IP Range**: `192.168.1.0/24` (local network)

---

## 🧪 Nmap Commands Used

| `ifconfig` 
| `nmap -sS 192.168.1.0/24` 
| `nmap -sA 192.168.1.0/24` 
| `nmap -sA 192.168.1.0/24 -oX scan.xml` 
| `xsltproc scan.xml -o scan.html` 
| `nmap -sS -sV -O 192.168.1.0/24` 

---

## 📥 Output Files

- `scan.xml`: Nmap scan result in XML format
- `scan.html`: Human-readable HTML version of the scan
- `scan_results_tcp.txt`: (Optional) Plain text output of TCP scan

---

## 📸 Wireshark Traffic Capture

### 🔍 Scan Monitored:
```bash
nmap -sS -sV -O 192.168.1.0/24
```

🔎 Wireshark Filters Used

- tcp.flags.syn == 1 && tcp.flags.ack == 0	
- tcp.flags.syn == 1 && tcp.flags.ack == 1	
- tcp.flags.reset == 1

-----

> 📌 Note: Due to technical limitations, the Nmap scan outputs were captured as screenshots instead of saved as files.
