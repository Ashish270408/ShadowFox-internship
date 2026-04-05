# Directory Bruteforce using Gobuster

## Objective
To discover hidden directories and files on the target web application.

## Target
http://testasp.vulnweb.com

## Environment
- OS: Kali Linux
- Tool: Gobuster
- Wordlist: /usr/share/wordlists/dirb/common.txt

## Command Used
gobuster dir -u http://testasp.vulnweb.com -w /usr/share/wordlists/dirb/common.txt -o result.txt

## Command Explanation
- `dir` → Directory brute force mode  
- `-u` → Target URL  
- `-w` → Wordlist used  
- `-o` → Save output  

## Key Findings
Discovered directories:
- /images (301)
- /templates (301)
- /avatars (301)
- /aspnet_client (301)
- /robots.txt (200)
- /cgi-bin (403)

## Analysis
- Status code 200 → Resource accessible  
- Status code 301 → Redirected but exists  
- Status code 403 → Exists but access restricted  

The presence of `robots.txt` may reveal hidden or restricted paths.  
403 responses indicate that directories exist but are protected.

## Security Insight
Hidden directories can expose sensitive information such as:
- Configuration files  
- Backup files  
- Admin panels  

Attackers use directory enumeration to find unprotected endpoints.

## Conclusion
Directory brute forcing successfully revealed multiple hidden paths that could be further tested for vulnerabilities.
