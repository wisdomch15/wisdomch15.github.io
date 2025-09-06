# Default Gateway Configuration

## TOOLS USED
- VirtualBox
- Kali Linux / Ubuntu VMs
- Optional: pfSense (or use one Linux VM as a router)

---

## INTRODUCTION
In this lab, I configured default gateways on VMs to enable communication between different subnets.  
Without a default gateway (router), machines on separate subnets cannot reach each other. By adding a gateway, traffic is routed correctly between networks.

---

## STEPS

### Step 1: 
Create Two Subnets
- Subnet A: `192.168.1.0/24`
- Subnet B: `192.168.2.0/24`

VM1 (Subnet A): `192.168.1.10/24`  
VM2 (Subnet B): `192.168.2.10/24`

### Step 2: Set Up a Router
Option A (pfSense):
- Add two network interfaces (one for each subnet).
- Assign:  
  - `192.168.1.1` to Subnet A interface.  
  - `192.168.2.1` to Subnet B interface.  

Option B (Linux Router):
- Use a Linux VM with two NICs.
- Assign IPs:
  ```bash
  sudo ip addr add 192.168.1.1/24 dev eth0
  sudo ip addr add 192.168.2.1/24 dev eth1
  sudo sysctl -w net.ipv4.ip_forward=1
