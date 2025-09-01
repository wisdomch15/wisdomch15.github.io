# Packet Sniffing and Analysis

TOOLS USED

Wireshark\
VirtualBox\
Kali Linux

INTRODUCTION

In this lab, I used Wireshark to capture and analyze network traffic. The goal was to identify protocols, inspect packets and detect suspicious activity.

STEPS

Step 1:\
I launched Wireshark on VirtualBox and selected the 'eth0' interface for packet capture.

Step 2:\
I started capturing and generated some HTTP traffic by visiting 'http://testphp.vulnweb.com'.

Step 3:\
I applied th efilter 'HTTP' to only show HTTP traffic.

Step 4:\
I followed a TCP stream to see the full HTTP request and response.

FINDINGS

- I was able to see HTTP requests in plaintext.  
- Usernames and passwords over HTTP can be intercepted.  
- This demonstrates why HTTPS is critical.
