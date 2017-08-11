# DHCP Server Checker

This python script checks whether it is able to acqiure an IP as a relay server.

It is written in pure python3 and has no external dependencies. It should therefore run on any system with python3 (untested).

## Examples

```bash
$ check_dhcp_relay -H 192.168.1.1 -r 192.168.1.10 -n 192.168.2.0 -m 255.255.255.0
```
This will reqest an ip from 192.168.1.1 from the network 192.168.2.0/24

## Nagios/Icinga 1.x config

```
# 'check_dhcp_relay' command definition
define command {
        command_name    check_dhcp_relay
        command_line    sudo /usr/lib/nagios/plugins/check_dhcp_relay -H '$HOSTADDRESS$' -r $ARG1$ -n $ARG2$ -m $ARG3$
}
```
