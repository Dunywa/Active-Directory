# Active Directory + DHCP + DNS Redundant Setup in Multi-Site Environment

---

## 🧭 Objective / Scenario
This project simulates a multi-site corporate network where two branch offices are connected using Windows Server Routing & Remote Access Service (RRAS) to establish a secure site-to-site VPN. Each site hosts a Windows Server 2022 Domain Controller providing AD, DNS, and DHCP with failover

The objective is to showcase real MSP-style infrastructure skills using Windows Server only (no PFsense or 3rd-party firewall), including:

- RRAS routing & IPSec VPN

- Multi-site Active Directory

- DHCP Failover

- DNS integration

- AD Sites & Services replication

- Multi-subnet domain join & routing

This project demonstrates proficiency across Microsoft infrastructure, routing, VPN, and enterprise network design.

---

## 🌐 Network Topology Diagram
Each RRAS server acts as:

- WAN router/gateway

- Firewall

- VPN tunnel endpoint

- Inter-subnet router

---

## ⚙️ Requirements / Environment
List all **hardware**, **software**, and **tools** used.

| Component | Description |
|------------|--------------|
| **Servers** | Windows Server 2022 and Windows Server 2025 |
| **Clients** | Windows 10 Pro (2x) |
| **Firewalls / Routers** | Windows Server2019 (2x) |
| **Hypervisor** | Hyyper-V |
| **Network Setup** | HQ – 192.168.10.0/24, Branch – 192.168.20.0/24 |
| **Other Tools** | PowerShell, Server Manager, Event Viewer |

---

## 🧩 Design Plan / Steps Overview
Provide a **high-level roadmap** of the configuration steps before execution.  

> **Example:**
> 1. Configure PFsense routers and VPN  
> 2. Promote two Windows Servers as Domain Controllers  
> 3. Configure DHCP scopes per subnet  
> 4. Configure DNS replication  
> 5. Test site-to-site communication and failover  

*(This section shows your project flow before you dive into details.)*

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

