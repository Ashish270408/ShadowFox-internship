# Network Traffic Analysis using Wireshark

## Objective
To capture and analyze network traffic and identify sensitive information transmitted over the network.

## Target
http://testasp.vulnweb.com

## Environment
- OS: Kali Linux
- Tool: Wireshark

## Methodology
1. Started packet capture on active interface (eth0)
2. Performed login on target website
3. Applied filter:
   http
4. Identified HTTP POST requests
5. Used "Follow HTTP Stream" to inspect data

## Key Findings
- Login credentials were transmitted in plain text
- Extracted credentials:
  - Username: user123
  - Password: pass1234

## Analysis
Since the application uses HTTP instead of HTTPS, data is not encrypted.

This allows attackers to:
- Intercept packets
- Read sensitive data directly
- Reconstruct communication streams

## Vulnerability Identified
**Sensitive Data Exposure (Plaintext Transmission)**

## Impact
- Credentials can be stolen easily
- Leads to unauthorized access
- Risk of account takeover

## Security Insight
Any application transmitting sensitive data over HTTP is vulnerable to packet sniffing attacks.

## Mitigation
- Use HTTPS (SSL/TLS encryption)
- Avoid transmitting credentials in plain text
- Implement secure authentication mechanisms

## Conclusion
This task demonstrated a critical vulnerability where sensitive user credentials were exposed due to lack of encryption.
