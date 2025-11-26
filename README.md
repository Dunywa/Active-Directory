# 🧰 Project Title
> *Enter a clear, professional project title here.*

**Example:**  
“Active Directory + DHCP + DNS Redundant Setup in Multi-Site Environment”

---

## 🧭 Objective / Scenario
Explain **why** you did this project and **what problem** it solves or simulates.

> **Example:**  
> Simulate a multi-site organization with redundancy, centralized management, and automated IP assignment using Windows Server and PFsense.

Include:
- Business or technical motivation  
- Scope (lab or production simulation)  
- Goals of the project  

---

## 🌐 Network Topology Diagram
Visualize your setup with a **simple, clear diagram**.

> Tools: Draw.io, Lucidchart, PFsense screenshots, or ASCII diagram.

**Example:**


*(Attach your diagram image below)*  
`![Network Diagram](./diagram.png)`

---

## ⚙️ Requirements / Environment
List all **hardware**, **software**, and **tools** used.

| Component | Description |
|------------|--------------|
| **Servers** | Windows Server 2022 (2x) |
| **Clients** | Windows 10 Pro (2x) |
| **Firewalls / Routers** | PFsense (2x) |
| **Hypervisor** | VMware Workstation / ESXi |
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

