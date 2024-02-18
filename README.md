## Secure Personal Computer Hardening Configuration Guide: Debian

This repository is intended to guide the user with tweaks to optimize Debian security for personal use.

Source: 

- https://wiki.debian.org/SetupGuides/SecurePersonalComputer#Introduction
- https://nlnetlabs.nl/documentation/unbound/howto-turnoff-dnssec/
- https://blog.remontti.com.br/6506

Phases:

## Configure Unbound DNS Local:

1 - Clone this repository.

2 - Install unbound on Debian.

```bash
sudo apt install unbound -y
```

3 - Change the file name using the command below and add it to the /etc/unbound directory:

```bash
# mv unbound-root-auto-trust-anchor-file.conf root-auto-trust-anchor-file.conf
# cp -p -R root-auto-trust-anchor-file.conf /etc/unbound/unbound.conf.d  
```
4 - Configuring Linux to use the loopback DNS server as a DNS server:
```bash
# echo "nameserver 127.0.0.1" > /etc/resolv.conf
# echo "nameserver ::1 " >> /etc/resolv.conf
```
5 - Install the dnsutils package to have testing tools:
```bash
# apt install dnsutils
```
6 - Result:

```bash
# host google.com 127.0.0.1

Using domain server:
Name: 127.0.0.1
Address: 127.0.0.1#53
Aliases: 
google.com has address 142.250.218.78
google.com has IPv6 address 2800:3f0:4001:81d::200e
google.com mail is handled by 10 smtp.google.com.
```
