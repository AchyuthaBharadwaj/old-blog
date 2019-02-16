---
title: "Reflector"
date: 2018-02-20
tags: [Security, Reflector, Python]
excerpt: "Created a “reflector” which will relaunch attacks sent to a given ip address and ethernet address to the IP address that sent the attack." 
mathjax: "true"
---

[link to repository](https://github.com/AchyuthaBharadwaj/Reflector-python)

The goal of this project is to create a “reflector” which will relaunch attacks sent to a given ip address and ethernet address to the IP address that sent the attack. This acts as a mirror, such that when an adversary is portscanning a network, they will actually be portscanning themselves. When they launch an exploit at the reflector, the attack will be reflected back at them.

This project is written in Python 2.7.

## Interface

The program can be run using the following command-line interface (all parameters are required, but not necessarily in this order):

    ./reflector --interface eth0 --victim-ip 192.168.1.10  --victim-ethernet 31:16:A9:63:FF:83 --reflector-ip 192.168.1.20 --reflector-ethernet 38:45:E3:89:B5:56

The program listens to the given network interface, and any IP, TCP, or UDP packets sent to the given victim IP address is taken and sent (without modification) on the given interface to the src IP from the reflector IP address. Then, when there is a response from the src IP address to the reflector IP address, that response is sent back to the src IP address as if it was from the victim IP address.

In this way, the program will impersonate two IP address (victim and reflector), and any packets that are sent to the victim will get re-sent to the src IP from the reflector IP. One good way to test this is to try to SSH to the victim IP from a machine that you have SSH access. You should find yourself SSHing into that same machine.