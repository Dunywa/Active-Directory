# Active Directory + DHCP + DNS Redundant Setup in Multi-Site Environment

---

## 🧭 Objective / Scenario
This project simulates a multi-site corporate network where two branch offices are connected using Windows Server Routing & Remote Access Service (RRAS) to establish a secure site-to-site VPN. Each site hosts a Windows Server 2022 Domain Controller providing AD, DNS, and DHCP with failover

The objective is to showcase real MSP-style infrastructure skills using Windows Server only, including:

- RRAS routing & IPSec VPN

- Multi-site Active Directory

- DHCP Failover

- DNS integration

- AD Sites & Services replication

- Multi-subnet domain join & routing

This project demonstrates proficiency across Microsoft infrastructure, routing, VPN, and enterprise network design.

---

## 🌐 Network Topology Diagram
|  Site                |  Domain Controller  |  LAN Subnet          | DC Server IP   | Router IP     | WAN IP        | Description   | 
|----------------------|---------------------|------------------|----------------|---------------|---------------|---------------|
| Headquarters (HQ)    | MVHO-DC1            | 192.168.1.0/24   | 192.168.1.1    | 192.168.1.1   | 10.0.0.1      | Main DC Site  |
|Branch Office (BO)    | MVBO-DC2            | 192.168.2.0/24   | 192.168.2.2    | 192.168.2.1   | 10.0.0.2      | Remote DC Site| 

Each subnet is connected via a site-to-site link (VPN or static route between routers).
So DC1 and DC2 can ping each other across subnets.

Each RRAS server acts as:

- WAN router/gateway

- Firewall

- VPN tunnel endpoint

- Inter-subnet router

---

## ⚙️ Requirements / Environment
| Component | Description |
|------------|--------------|
| **Servers** | Windows Server 2022 and Windows Server 2025 |
| **Clients** | Windows 10 Pro (2x) |
| **Firewalls / Routers** | Windows Server 2019 and 2022 |
| **Hypervisor** | Hyyper-V |
| **Other Tools** | PowerShell, Server Manager, Event Viewer |

---

## 🧩 Design Plan / Steps Overview

- Configured site-to-site VPN (IPSec Tunnel) to connect the two sites  
- Promote two Windows Servers as Domain Controllers  
- Configure DHCP scopes per subnet  
- Configure DNS replication  
- Test site-to-site communication and failover

---

## 🛠️ Implementation (Execution)
Document how you **implemented** each major step.  
Focus on **what was done**, key **PowerShell commands**, and **screenshots** — not click-by-click instructions.

**Example Format:**
### Step 1: Configure PFsense VPN
- Created IPSec VPN tunnel between sites.  
- Allowed required AD and DNS ports.  
- Verified connectivity with ICMP.

**Example Screenshot:**
`![PFsense VPN Config](./pfsense-vpn.png)`

**Example Command:**
```powershell
Test-Connection -ComputerName DC2 -Count 4

