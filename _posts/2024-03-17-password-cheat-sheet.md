---
title: "Password cheat sheet"
date: 2024-03-17
---
## Hashcat
To brute-force blowfish hashes using `rockyou.txt` wordlist:
```
hashcat -m 3200 hashes.txt /usr/share/wordlists/rockyou.txt
```
The type of hash can be deduced using hashcat:
```
hashcat hashes.txt
```
Or using hashid:
```
hashid $2a$10$SpKYdHLB0FOaT7n3x72wtuS0yR8uqqbNNpIPjUb2MZib3H9kVO8dm
```
It is also possible to prefix the hashes with a username in the hash file (for instance `user:$2a$10...`). If you do that, you should use the option `--user` of `hashcat`.