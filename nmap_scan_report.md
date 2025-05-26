# Nmap Scan Report

## 🔧 Commands Used  with Explanation

- `ifconfig`  
  - Purpose: To find the local IP address of my device.
  - Result: Found my local IP as 192.168.1.6

- `nmap -sS 192.168.1.0/24`  
   - TCP SYN scan (also called "half-open" scan)
   - To discover live hosts and detect which TCP ports are open without completing the full handshake.
   - Found active IPs in my network and their open TCP ports
 
  - [TCP SYN Scan - 1](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/TCP%20SYN%20scan(1).png)
  - [TCP SYN Scan - 2](https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/TCP%20SYN%20scan%20(2).png)
 

- `nmap -sS -sV -O 192.168.1.0/24`
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

  - [Scan result through firefox)[https://github.com/deepthiii33/Elavate_Labs_task-1/blob/main/screenshots/scan_result_in_firefox.png]

  


- `nmap -sS -sV -O 192.168.1.0/24`  
  ➤ Full service and OS detection


Command: nmap -sS 192.168.1.0/24



