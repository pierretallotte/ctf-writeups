---
title: "Fuff cheat sheet"
date: 2024-03-17
---
## Hidden pages and directories
```
ffuf -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-big.txt:FUZZ -u http://DOMAIN_NAME:PORT/FUZZ -ic -v
```
## Hidden vhosts
```
ffuf -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-110000.txt:FUZZ -u http://DOMAIN_NAME:PORT/ -H 'Host: FUZZ.DOMAIN_NAME' -ic -v
```
### Hidden POST parameters
```
ffuf -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ -u http://DOMAIN_NAME:PORT/PAGE -X POST -d 'FUZZ=something' -H 'Content-Type: application/x-www-form-urlencoded' -fs SIZE
```