[**<= BACK**](packetsniffing.md)<br><br>
# Default Gateway Configuration

## TOOLS USED
- VirtualBox
- 2 Kali Linux VMs
- pfSense 

## INTRODUCTION
In this lab, I configured a default gateway on a VM to enable communication between different subnets.  
Without a default gateway, machines on separate subnets cannot reach each other. By adding a gateway, traffic is routed correctly between networks.

## STEPS

### Step 1: 
I created 2 subnets on virtual box and called them `network1` and `network2`

### Step 2: 
I connected one VM to `network1` and the other to `network2`

### Step 3: 
I added two network interfaces on pfSense and assigned `192.168.1.1` as LAN1 and `192.168.2.1` as LAN2 interface. 

### Step 4: 
On the first VM, I manually set the IP address to `192.168.1.10/24` and the gateway to `192.168.1.1`. On the second VM, I manually set the IP address to `192.168.2.10/24` and the gateway to `192.168.2.1`  

### Step 5:  
On pfSense, I created firewall rules to allow traffic between LAN1 and LAN2, by going on `https://192.168.1.1`.

### Step 6:  
I tested connectivity by pinging from the first VM `192.168.1.10` to the second VM `192.168.2.10` and vice versa. 


## FINDINGS
- Without a default gateway, VMs on different subnets could not reach each other.  
- After setting the default gateway to pfSense and adding firewall rules, communication between subnets became possible.  

## CONCLUSION
This lab demonstrated how pfSense can act as a router between two isolated subnets. By configuring IP addresses, default gateways, and firewall rules, inter-subnet communication was established. Furthermore, restricting firewall rules is essential to maintain security.
