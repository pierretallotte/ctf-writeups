---
title: "Fuff cheat sheet"
date: 2024-02-04
---
## Hidden pages and directories
```
ffuf -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-big.txt:FUZZ -u http://DOMAIN_NAME/FUZZ -ic -v
```