## Secure Personal Computer Hardening Configuration Guide: Debian

This repository is intended to guide the user with tweaks to optimize Debian security for personal use.

Source: 

- https://wiki.debian.org/SetupGuides/SecurePersonalComputer#Introduction
- https://nlnetlabs.nl/documentation/unbound/howto-turnoff-dnssec/
- https://blog.remontti.com.br/6506

Phases:

1 - Clone this repository.
2 - Install unbound on Debian.
    ```bash
    sudo apt install unbound -y
    ```
3 - Change the file name using the command below and add it to the /etc/unbound directory:
4 - Change the file name using the command below:
```bash
# mv unbound-root-auto-trust-anchor-file.conf root-auto-trust-anchor-file.conf
# cp -p -R root-auto-trust-anchor-file.conf /etc/unbound/unbound.conf.d  
```

