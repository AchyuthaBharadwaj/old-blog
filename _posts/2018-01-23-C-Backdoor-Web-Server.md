---
title: "C Backdoor “Web Server”"
date: 2018-01-23
tags: [Security, C, Web Server, Backdoor, Sockets]
excerpt: "A minimal HTTP 1.1 server, based on RFC 2616 from scratch, without using any libraries except for the C standard library." 
mathjax: "true"
---

[link to repository](https://github.com/AchyuthaBharadwaj/Web-Server-using-C-sockets)

A critical part of establishing persistence on a system is to leave a “backdoor” that allows the hacker access to the system at a later date, without exploiting the same vulnerabilities (they may be fixed in the meantime). In this Project, I created a backdoor that pretends to be a web server. A web server makes a great pretense for a backdoor, because web traffic is so prevalent it does not raise red flags and ports 80 and 443 are frequently permitted through firewalls.

This is a minimal HTTP 1.1 server, based on RFC 2616 from scratch, without using any libraries except for the C standard library.

## Interface

This web server program takes one command line argument $$port\_number$$. It listens for incoming connections to the given port, and responds to most requests with a valid HTTP 1.1 response with the 404 HTTP response code. 

It supports valid HTTP 1.1 requests from HTTP clients, and server should never cause the client to hang or otherwise malfunction (otherwise the backdoor will be detected).

The backdoor functionality is that when server receives a GET request for a URL in the form of /exec/`<command>`, then the server takes `<command>` and executes it using the system popen and the HTTP response is the stdout of the executed command. The HTTP status code of the response is 200, even if the command exec fails. There are no limitations to the characters in `<command>`, the program captures the rest of the requested URL from the / after /exec to the end of the URL.

For instance, an HTTP GET of /exec/ls will return an HTTP response with the body of the output of the execution of the ls command on the server. An HTTP GET of /exec/ls%20-la will return an HTTP response with the body of the output of ls -la.

When the server is killed (Control-C via command prompt or the SIGINT signal is sent to the program), the server releases the port and safely terminates.

## Implementation
program works on Ubuntu 16.04 64-bit with the default packages installed. 