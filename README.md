# DHCP Server Checker

This python script checks whether it is able to acqiure an IP as a relay server.

It is written in pure python3 and has no external dependencies. It should therefore run on any system with python3 (untested).

## Requirements

Python3

Needs to be run as root

## Usage

```
usage: check_dhcp_relay [-h] -H HOST -r RELAY -n NETWORK -m MASK [-t TIMEOUT]
                        [-l LISTEN] [-c MAC] [--no-release] [--verbose]
```

Example:
```bash
$ check_dhcp_relay -H 192.168.1.1 -r 192.168.1.10 -n 192.168.2.0 -m 255.255.255.0
DHCP OK | responsetime=0.01ms
```

## Nagios/Icinga 1.x config

```
# 'check_dhcp_relay' command definition
define command {
        command_name    check_dhcp_relay
        command_line    sudo /usr/lib/nagios/plugins/check_dhcp_relay -H '$HOSTADDRESS$' -r $ARG1$ -n $ARG2$ -m $ARG3$
}
```
