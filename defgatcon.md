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
