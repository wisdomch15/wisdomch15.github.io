# IP Address Assignment Lab

## TOOLS USED

- VirtualBox  
- Kali Linux / Ubuntu  
- Terminal (ip command)

---

## INTRODUCTION

In this lab, I practiced how to manually configure a static IP address inside a Linux VM running in VirtualBox. This is an important step for understanding subnetting, IP configuration, and how devices communicate on a network.

---

## STEPS

**Step 1:**  
I opened the terminal in my Kali Linux VM.

**Step 2:**  
I assigned the static IP `192.168.1.10/24` to the `eth0` interface using the following command:  
```bash
sudo ip addr add 192.168.1.10/24 dev eth0

