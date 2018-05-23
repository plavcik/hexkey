hexkey
======

Python 3 tool to generate hexkey for ifconfig in [OpenBSD](https://www.openbsd.org/).

Command [ifconfig(8)](https://man.openbsd.org/ifconfig.8) is used in OpenBSD to configure network interfaces. For WLAN (IEEE 802.11 specifications) with WPA key, the key can be given using a full length hex key. This **hexkey** toll can generate that hex key from these three inputs:

* wireless interface (that's only needed for printing complete ifconfig command)
* network ID (ESSID)
* WPA key (passphrase to access network above)


Usage
-----

As regular user:

1. edit `hexkey.py` and fill in variables **interface**, **nwid** and **passphrase**
2. run `hexkey.py`, which will print ifconfig command including generated hex key


Notes
-----

* printed command is using [doas(1)](https://man.openbsd.org/doas.1) (successor to sudo) to execute command as root
* make sure, that passphrase and/or hex key can't be seen by surrounding

Code has been checked for code style via

```shell
pycodestyle --show-source --show-pep8 hexkey.py
```
