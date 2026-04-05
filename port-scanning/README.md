# Port Scanning using Nmap

## Objective
To identify open ports and services running on the target web application in order to understand potential attack surfaces.

## Target
http://testasp.vulnweb.com

## Environment
- OS: Kali Linux (Virtual Machine)
- Tool: Nmap

## Command Used
nmap -p- -sV testasp.vulnweb.com -oN scan.txt

## Command Explanation
- `-p-` → Scans all 65535 TCP ports  
- `-sV` → Detects service versions  
- `-oN` → Saves output to a file  

## Key Findings
- Host was active and reachable  
- Majority of ports were filtered (likely due to firewall)  
- Port 80 was open  
- Service running: Microsoft IIS httpd 8.5  

## Analysis
The presence of port 80 confirms that the web server is accessible over HTTP.  
Filtered ports indicate that security controls such as firewalls are in place.

Identifying service versions is important because outdated software may contain known vulnerabilities.

## Security Insight
Open ports increase the attack surface of a system.  
If services are not properly secured or updated, attackers can exploit them.

## Conclusion
Port scanning successfully identified the active service and potential entry point for further security testing.
