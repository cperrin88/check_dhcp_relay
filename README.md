# DHCP Server Checker

This python script checks whether it is able to acqiure an IP as a relay server.

It is written in pure python3 and has no external dependencies. It should therefore run on any system with python3 (untested).

## Examples

```bash
$ check_dhcp_relay -H 192.168.1.1 -r 192.168.1.10 -n 192.168.2.0 -m 255.255.255.0
```
This will reqest an ip from 192.168.1.1 from the network 192.168.2.0/24
