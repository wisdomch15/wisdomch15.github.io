# Packet Sniffing and Analysis

TOOLS USED

Wireshark\
VirtualBox\
Kali Linux

INTRODUCTION

In this lab, I used Wireshark to capture and analyze network traffic. The goal was to identify protocols, inspect packets and detect suspicious activity.

STEPS

Step 1:\
I launched Wireshark on VirtualBox and selected the 'eth0' interface for packet capture.\
![image](image1.jpg)\
![image3](image3.jpg)

Step 2:\
I started capturing and generated some HTTP traffic by visiting 'http://testphp.vulnweb.com'.\
![image2](image2.jpg)

Step 3:\
I applied the filter 'HTTP' to only show HTTP traffic.\
![image4](image4.jpg)

Step 4:\
I followed a TCP stream to see the full HTTP request and response.
![image6](image6.jpg)
![image7](image7.jpg)
FINDINGS

- I was able to see HTTP requests in plaintext.  
- Usernames and passwords over HTTP can be intercepted.  
- This demonstrates why HTTPS is critical.

CONCLUSION

Packet sniffing helps analysts understand normal vs. suspicious traffic. This lab showed me how to capture and analyze traffic using Wireshark.
