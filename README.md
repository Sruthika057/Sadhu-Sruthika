#Task 1 : Scan Your local network for open ports 

##What the Task Was

The objective of this task was to perform a basic network reconnaissance on my local network using Nmap. The goal was to identify live devices, discover open ports, and analyze potential security exposures based on the services running on those ports.

##Tools Used

Nmap (via Zenmap GUI)
Windows Command Prompt (`ipconfig`) for checking local IP

## Steps I Followed

1. Installed Nmap/Zenmap from the official site.
2. Found my local IP address using:
   ```
   ipconfig
   ```
3. Identified my subnet as `192.168.1.0/24`
4. Performed a TCP SYN scan using Zenmap with
   nmap -sS 192.168.1.0/24
5. Collected scan results and saved them as `scan_results.txt`
6. Took a screenshot of the Zenmap output
7. Analyzed the ports and services discovered

   ## What I Found

Out of multiple devices scanned, one device (192.168.1.1, likely the router) had the following open ports:

| Port | Service | Description |
|------|---------|-------------|
| 22   | SSH     | Secure remote login (normal for routers) |
| 23   | Telnet  | Unencrypted remote login (potential risk) |
| 53   | DNS     | Domain name resolution |
| 80   | HTTP    | Likely web admin page of router |
| 1900 | UPnP    | Universal Plug and Play (known to be risky) |

Other devices were detected as live hosts and no open ports (ports were filtered or reset), which is a good security practice. while few other devices has the open ports ( which i recorded in the screenshots and uploaded in the screenshot folder)

## Potential Security Risks
By understanding about different ports i can to know that certain ports possess the potential security risks and are highly vulnerable 

Telnet (port 23): This protocol is outdated and insecure; it transmits data in plain text and is vulnerable to eavesdropping.
UPnP (port 1900): Frequently associated with vulnerabilities and often exploited in attacks. It’s best to disable UPnP unless strictly needed.

##  What I Learned

- How to scan a local subnet using Nmap
- How to identify live hosts and open ports
- How to analyze services running on those ports
- Basic understanding of what constitutes a security risk in a network
- How to export and document scan results for reporting

Project Files:
 scan_results.txt— Full output from Zenmap
 screenshot folder — Zenmap scan screenshot

 README.md — Documentation of task
