[**<= BACK**](subipconfig.md)<br><br>
# Ping and Connectivity Test

## TOOLS USED
- VirtualBox (Internal Network)
- Two Linux VMs (Kali/Ubuntu)
- Terminal: `ip`, `ping`, `tcpdump` (optional)

## INTRODUCTION
This lab demonstrates how IP configuration affects connectivity. Two VMs are placed on the same Layer-2 network. First, they are configured in the **same subnet** (ping succeeds). Then one VM is moved to a **different subnet without a router** (ping fails).

## STEPS

### Step 1 — VirtualBox network setup
1. In VirtualBox, go to **File → Tools → Network** → **Create** an **Internal Network** (name it `labnet`).  
2. For **VM1** and **VM2**:
   - **Settings → Network**  
   - **Adapter 1**: *Disable* (to avoid default routes via NAT and keep the test clean).  
   - **Adapter 2**: **Enable** → **Attached to:** *Internal Network* → **Name:** `labnet`.

> Screenshot: VirtualBox adapters for both VMs

### Step 2 — Identify the interface inside each VM
In each VM:
```bash
ip -br a
