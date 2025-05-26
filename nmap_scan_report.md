# Nmap Scan Report

## 🔧 Commands Used  with Explanation

1. `ifconfig`  
  - Purpose: To find the local IP address of my device.
  - Result: Found my local IP as 192.168.1.6

2. `nmap -sS 192.168.1.0/24`  
   - TCP SYN scan (also called "half-open" scan)
   - To discover live hosts and detect which TCP ports are open without completing the full handshake.
   - Found active IPs in my network and their open TCP ports
 
  - [TCP SYN Scan - 1](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/TCP%20SYN%20scan(1).png)
  - [TCP SYN Scan - 2](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/TCP%20SYN%20scan%20(2).png)
 
 
####  **Active IPs and Their Ports/Services**


| IP Address     | Open Ports                | Services                                      | Notes                        |
|----------------|---------------------------|-----------------------------------------------|------------------------------|
| 192.168.1.1    | 53, 80, 443                | domain (DNS), http, https                     | Some ports filtered (21,22,23) |
| 192.168.1.2    | 135, 139, 445, 8080, 8899  | msrpc, netbios-ssn, microsoft-ds, http-alt, unknown | Many high ports closed       |
|                | 9090 (closed), 50000–50005, 50030, 50036 (closed) | ibm-db2, iimfsf, unknown     |                              |
| 192.168.1.3    | None                      | All ports closed or ignored                  |                              |
| 192.168.1.4    | None                      | All ports closed or ignored                  |                              |
| 192.168.1.6    | None                      | All ports closed or ignored                  |                              |
| 192.168.1.8    | None                      | All ports closed or ignored                  | Hostname: dc-2               |



####  **Scan Summary**

* **Total Active IPs**: 6 (from the 256 scanned)
* **Hosts with open ports**: 192.168.1.1, 192.168.1.2
* **Hosts with all ports closed/ignored**: 192.168.1.3, 192.168.1.4, 192.168.1.6, 192.168.1.8


 

3. `nmap -sS -sV -O 192.168.1.0/24`
   - -sS: TCP SYN scan
   - -sV: Version detection (detects service version)
   - -O: OS detection (identify operating systems)
 
   - To know what services they run and possibly what OS they are using.
 
   - [Example](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/nmap_service_os_scan.png)

### 💾 Saving Nmap Output as HTML

 - ` nmap -sA 192.168.1.0/24 -oX scan.xml `
 - `xsltproc scan.xml -o scan.html `

  - [TCP ACK scan](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/nmap_ack_scan.png)

  - Scan Type: TCP ACK scan.
  - nmap -sA 192.168.1.0/24: Performs a TCP ACK scan on the local network.
  - -oX scan.xml: Saves the scan results in XML format.
  - xsltproc (XSLT processor for transforming XML files) - Which converts the XML Nmap output (scan.xml) into a readable HTML file (scan.html).

  - Now we cam open scan.html in any browser (like Firefox or Chrome) to view the scan results in a nicely formatted way.

  - [Scan result through firefox](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/scan_result_in_firefox.png)

  
--- 
### Nmap Scan Conclusion 
Running the Nmap scans helped me understand how devices on a local network communicate and what services they’re running. With just a few commands, I was able to:Discover all active devices in my network , Find which ports were open, and what services (like HTTP, SSH, etc.) were running on them.



