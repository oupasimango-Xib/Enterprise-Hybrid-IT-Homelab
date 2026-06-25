<!-- HEADER BANNER -->
<p align="center">
  <img src="https://img.shields.io/badge/Windows_Server_2025-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows Server 2022">
  <img src="https://img.shields.io/badge/Microsoft_365-0078D4?style=for-the-badge&logo=microsoft-365&logoColor=white" alt="Microsoft 365">
  <img src="https://img.shields.io/badge/Entra_ID-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white" alt="Entra ID">
  <img src="https://img.shields.io/badge/Intune-0078D4?style=for-the-badge&logo=microsoft-intune&logoColor=white" alt="Intune">
  <img src="https://img.shields.io/badge/SharePoint-0078D4?style=for-the-badge&logo=sharepoint&logoColor=white" alt="SharePoint">
  <img src="https://img.shields.io/badge/Teams-6264A7?style=for-the-badge&logo=microsoft-teams&logoColor=white" alt="Teams">
  <img src="https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge&logo=powershell&logoColor=white" alt="PowerShell">
  <img src="https://img.shields.io/badge/Active_Directory-0078D4?style=for-the-badge&logo=microsoft&logoColor=white" alt="Active Directory">
</p>

# 🏢 Enterprise Hybrid IT Homelab

<p align="center">
  <strong>End-to-End Enterprise Infrastructure Project</strong><br>
  <em>On-Premises Active Directory · Microsoft 365 · Entra ID · Intune · SharePoint · Teams</em>
</p>

<p align="center">
  <a href="#-project-overview">Overview</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-implementation-phases">Implementation</a> •
  <a href="#-skills-demonstrated">Skills</a> •
  <a href="#-author">Author</a>
</p>

---

## 📋 Project Overview

This homelab simulates a **real-world enterprise hybrid IT environment**, integrating on-premises infrastructure with Microsoft 365 cloud services. The project demonstrates the complete lifecycle of modern IT administration—from building a domain controller to managing cloud identities and deploying collaboration tools.

### 🎯 Objectives

| Objective | Status |
|-----------|--------|
| ✅ Build on-premises Active Directory infrastructure | Complete |
| ✅ Deploy DHCP and DNS services | Complete |
| ✅ Implement Group Policy security baselines | Complete |
| ✅ Configure Microsoft 365 tenant with custom domain | Complete |
| ✅ Synchronize identities using Entra ID Connect | Complete |
| ✅ Enroll Windows 11 client into Intune MDM | Complete |
| ✅ Deploy device compliance policies | Complete |
| ✅ Configure SharePoint, Teams, and Outlook | Complete |

---

## 🏗️ Architecture

### Virtual Machines

| VM | OS | RAM | Storage | Role |
|----|----|-----|---------|------|
| **DC01** | Windows Server 2025 | 4 GB | 80 GB | Domain Controller, DNS, DHCP, Entra Connect |
| **CLIENT01** | Windows 11 Enterprise | 4 GB | 64 GB | Domain-joined client, Intune-enrolled |

### Network Topology
┌───────────────────────────────────────────────────────────────┐
│ HOST MACHINE │
│ ┌──────────────────────────────────────────────────────────┐ │
│ │ INTERNAL ADAPTER (NAT) │ │
│ │ 192.168.1.0/24 │ │
│ │ │ │
│ │ ┌─────────────────┐ ┌────────────────────────┐ │ │
│ │ │ DC01 │ │ CLIENT01 │ │ │
│ │ │ 192.168.1.10 │ │ 192.168.1.100 │ │ │
│ │ │ AD + DNS + DHCP│ │ Domain-Joined │ │ │
│ │ │ Entra Connect │ │ Intune-Enrolled │ │ │
│ │ └─────────────────┘ └────────────────────────┘ │ │
│ │ │ │ │
│ │ EXTERNAL ADAPTER (Internet) │ │
│ │ Microsoft 365 Cloud Connectivity │ │
│ └──────────────────────────────────────────────────────────┘ │
└───────────────────────────────────────────────────────────────┘

---

## 📸 Implementation Phases

<details>
<summary><b>⚙️ Phase 1: On-Premises Infrastructure (Click to expand)</b></summary>

### System & Network Setup

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/00_System_Requirements.png" width="400"> | System requirements verification |
| <img src="screenshots/01_Vmware_Network_Adapters01.png" width="400"> | VMware network adapter configuration 1 |
| <img src="screenshots/01_Vmware_Network_Adapters02.png" width="400"> | VMware network adapter configuration 2 |
| <img src="screenshots/02_Network_Adapters_list.png" width="400"> | Network adapters list (Internal + NAT) |

### Static IP Configuration

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/03_Static_IP_Config.png" width="400"> | Static IP configuration for DC01 (192.168.1.10) |

### Active Directory Installation

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/04_ADDS_Installation01.png" width="400"> | AD DS role installation - step 1 |
| <img src="screenshots/04_ADDS_Installation02.png" width="400"> | AD DS role installation - step 2 |
| <img src="screenshots/05_Domain_Promotion.png" width="400"> | Domain promotion to contoso.com |
| <img src="screenshots/06_Verify_Domain.png" width="400"> | Domain verification after promotion |

### Organizational Units & Users

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/07_OU_Structure.png" width="400"> | OU structure (Users, Groups, Computers, ServiceAccounts) |
| <img src="screenshots/8_AD_Users01.png" width="400"> | Active Directory users - view 1 |
| <img src="screenshots/8_AD_Users02.png" width="400"> | Active Directory users - view 2 |
| <img src="screenshots/8_AD_Users03.png" width="400"> | Active Directory users - view 3 |

### User Properties

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/09_User_Properties01.png" width="400"> | User properties - General tab |
| <img src="screenshots/09_User_Properties02.png" width="400"> | User properties - Account tab |
| <img src="screenshots/09_User_Properties_LogonHours.png" width="400"> | User logon hours configuration |

</details>

<details>
<summary><b>🌐 Phase 2: Domain Join (Click to expand)</b></summary>

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/09_Domain_Login.png" width="400"> | Domain login screen (CONTOSO\jdoe) |
| <img src="screenshots/10_Domain_Join01.png" width="400"> | Domain join process - step 1 |
| <img src="screenshots/10_Domain_Join02.png" width="400"> | Domain join process - step 2 |
| <img src="screenshots/10_Domain_Success.png" width="400"> | Domain join success confirmation |

</details>

<details>
<summary><b>☁️ Phase 3: DHCP Configuration (Click to expand)</b></summary>

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/11_DHCP_Installed01.png" width="400"> | DHCP installation - step 1 |
| <img src="screenshots/11_DHCP_Installed02.png" width="400"> | DHCP installation - step 2 |
| <img src="screenshots/11_DHCP_Installed03.png" width="400"> | DHCP installation - step 3 |
| <img src="screenshots/12_DHCP_Scope.png" width="400"> | DHCP scope creation (192.168.1.100-192.168.1.200) |
| <img src="screenshots/13_DHCP_Options.png" width="400"> | DHCP options (DNS, Gateway, Domain) |

</details>

<details>
<summary><b>🔐 Phase 4: Group Policy Security (Click to expand)</b></summary>

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/15_GPO_Password_Policy.png" width="400"> | Password policy configuration |

**Configured Settings:**
- ✅ Password complexity enabled
- ✅ Minimum password length: 8 characters
- ✅ Maximum password age: 42 days
- ✅ Account lockout: 3 attempts

</details>

<details>
<summary><b>☁️ Phase 5: Microsoft 365 Setup (Click to expand)</b></summary>

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/16_M365_Admin_Dashboard.png" width="400"> | Microsoft 365 Admin Center dashboard |
| <img src="screenshots/17_M365_Users.png" width="400"> | Microsoft 365 users (synced from on-prem) |
| <img src="screenshots/18_M365_Licenses.png" width="400"> | License assignment (M365 E5) |

</details>

<details>
<summary><b>🔑 Phase 6: Hybrid Identity with Entra ID (Click to expand)</b></summary>

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/19_Security_Defaults.png" width="400"> | Security defaults enabled |
| <img src="screenshots/20_SSPR_Config.png" width="400"> | Self-Service Password Reset configuration |
| <img src="screenshots/21_Download_MicrosoftEntra_connect.png" width="400"> | Microsoft Entra Connect download |
| <img src="screenshots/22_MicrosoftEntra_installation.png" width="400"> | Entra Connect installation wizard |
| <img src="screenshots/23_MicrosoftEntra_Config.png" width="400"> | Entra Connect configuration - step 1 |
| <img src="screenshots/24_MicroEntra_Config.png" width="400"> | Entra Connect configuration - step 2 |
| <img src="screenshots/25_Sync_Service.png" width="400"> | Sync service running successfully |
| <img src="screenshots/26_AzureAD_Users.png" width="400"> | Azure AD users synced from on-prem |
| <img src="screenshots/27_AzureAD_User_Properties.png" width="400"> | Azure AD user properties |

</details>

<details>
<summary><b>💻 Phase 7: Device Enrollment (Intune) (Click to expand)</b></summary>

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/28_CLIENT01_Connect.png" width="400"> | CLIENT01 connecting to Azure AD |
| <img src="screenshots/29_Microsoft_Intune.png" width="400"> | Microsoft Intune dashboard with enrolled devices |

</details>

<details>
<summary><b>🛡️ Phase 8: Intune Compliance Policies (Click to expand)</b></summary>

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/30_Policy_summary.png" width="400"> | Policy summary dashboard |
| <img src="screenshots/31_Password_enforcement_configured.png" width="400"> | Password enforcement configuration |
| <img src="screenshots/32_Compliance_policy_summary.png" width="400"> | Compliance policy summary |
| <img src="screenshots/33_CLIENT01_Compliant.png" width="400"> | CLIENT01 showing compliant status |
| <img src="screenshots/34_CLIENT01_Compliant1.png" width="400"> | CLIENT01 compliance details - view 1 |
| <img src="screenshots/35_CLIENT01_Complient2.png" width="400"> | CLIENT01 compliance details - view 2 |

</details>

<details>
<summary><b>📧 Phase 9: Microsoft 365 Applications (Click to expand)</b></summary>

### Outlook

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/36_Inbox_sent_email.png" width="400"> | Outlook inbox with sent email |

### Microsoft Teams

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/37_Teams_home_screen.png" width="400"> | Teams home screen |
| <img src="screenshots/38_Team_created.png" width="400"> | IT Support Team created |
| <img src="screenshots/39_Members_added.png" width="400"> | Team members added |
| <img src="screenshots/40_Message_visible_Teams_chat.png" width="400"> | Message visible in Teams chat |

### SharePoint

| Screenshot | Description |
|------------|-------------|
| <img src="screenshots/41_SharePoint_home_page.png" width="400"> | SharePoint home page |
| <img src="screenshots/42_New_site_created.png" width="400"> | IT Department Site created |
| <img src="screenshots/43_File_visible_SharePoint_document_library.png" width="400"> | File visible in SharePoint document library |

</details>

---

## 🎯 Skills Demonstrated

<table>
  <tr>
    <td align="center"><b>🖥️ Active Directory</b></td>
    <td>Domain Controller setup, OU management, user provisioning, Group Policy</td>
  </tr>
  <tr>
    <td align="center"><b>☁️ Entra ID</b></td>
    <td>Hybrid identity configuration, directory synchronization, single sign-on</td>
  </tr>
  <tr>
    <td align="center"><b>📱 Microsoft Intune</b></td>
    <td>Device enrollment, compliance policies, configuration profiles, MDM</td>
  </tr>
  <tr>
    <td align="center"><b>📧 M365 Administration</b></td>
    <td>User management, license assignment, tenant configuration, Exchange Online</td>
  </tr>
  <tr>
    <td align="center"><b>🌐 Networking</b></td>
    <td>DHCP scope creation, DNS configuration, static IP allocation, NAT</td>
  </tr>
  <tr>
    <td align="center"><b>🔒 Security</b></td>
    <td>Password policies, conditional access, security defaults, compliance enforcement</td>
  </tr>
  <tr>
    <td align="center"><b>🤖 PowerShell</b></td>
    <td>Automation, scripting, AD management, M365 administration</td>
  </tr>
  <tr>
    <td align="center"><b>📊 Collaboration Tools</b></td>
    <td>SharePoint sites, Teams creation, OneDrive sync, Outlook configuration</td>
  </tr>
</table>

---

## 📊 Project Statistics

<table>
  <tr>
    <td align="center"><b>📸 Screenshots</b></td>
    <td align="center"><b>⚙️ Phases</b></td>
    <td align="center"><b>💻 VMs</b></td>
    <td align="center"><b>📦 Services</b></td>
  </tr>
  <tr>
    <td align="center">43</td>
    <td align="center">9</td>
    <td align="center">2</td>
    <td align="center">10+</td>
  </tr>
</table>

---

## 🏆 Key Achievements

- ✅ **100% Success Rate** — All components functional with zero failures
- ✅ **Hybrid Identity** — Seamless sync between on-prem AD and Entra ID
- ✅ **Zero-Trust Ready** — Conditional access policies configured
- ✅ **Modern Management** — Windows 11 enrolled in Intune with compliance policies
- ✅ **Collaboration Suite** — Full Microsoft 365 stack deployed and tested
- ✅ **Production-Ready** — Architecture mirrors enterprise standards

---

## 💡 Lessons Learned

<details>
<summary><b>Click to expand</b></summary>

1. **DNS is the backbone** — Misconfigured DNS breaks everything in hybrid environments
2. **Plan your sync scopes** — Only sync necessary OUs to avoid clutter in Entra ID
3. **Test compliance policies** — Test on a single device before deploying to all
4. **Document everything** — Screenshots saved hours of troubleshooting
5. **Security first** — MFA and conditional access are non-negotiable in hybrid setups

</details>

---

## 🔗 Repository Structure
Enterprise-Hybrid-IT-Homelab/
├── README.md
├── screenshots/
│ ├── 00_System_Requirements.png
│ ├── 01_Vmware_Network_Adapters01.png
│ ├── 01_Vmware_Network_Adapters02.png
│ ├── 02_Network_Adapters_list.png
│ ├── 03_Static_IP_Config.png
│ ├── 04_ADDS_Installation01.png
│ ├── 04_ADDS_Installation02.png
│ ├── 05_Domain_Promotion.png
│ ├── 06_Verify_Domain.png
│ ├── 07_OU_Structure.png
│ ├── 8_AD_Users01.png
│ ├── 8_AD_Users02.png
│ ├── 8_AD_Users03.png
│ ├── 09_Domain_Login.png
│ ├── 09_User_Properties_LogonHours.png
│ ├── 09_User_Properties01.png
│ ├── 09_User_Properties02.png
│ ├── 10_Domain_Join01.png
│ ├── 10_Domain_Join02.png
│ ├── 10_Domain_Success.png
│ ├── 11_DHCP_Installed01.png
│ ├── 11_DHCP_Installed02.png
│ ├── 11_DHCP_Installed03.png
│ ├── 12_DHCP_Scope.png
│ ├── 13_DHCP_Options.png
│ ├── 15_GPO_Password_Policy.png
│ ├── 16_M365_Admin_Dashboard.png
│ ├── 17_M365_Users.png
│ ├── 18_M365_Licenses.png
│ ├── 19_Security_Defaults.png
│ ├── 20_SSPR_Config.png
│ ├── 21_Download_MicrosoftEntra_connect.png
│ ├── 22_MicrosoftEntra_installation.png
│ ├── 23_MicrosoftEntra_Config.png
│ ├── 24_MicroEntra_Config.png
│ ├── 25_Sync_Service.png
│ ├── 26_AzureAD_Users.png
│ ├── 27_AzureAD_User_Properties.png
│ ├── 28_CLIENT01_Connect.png
│ ├── 29_Microsoft_Intune.png
│ ├── 30_Policy_summary.png
│ ├── 31_Password_enforcement_configured.png
│ ├── 32_Compliance_policy_summary.png
│ ├── 33_CLIENT01_Compliant.png
│ ├── 34_CLIENT01_Compliant1.png
│ ├── 35_CLIENT01_Complient2.png
│ ├── 36_Inbox_sent_email.png
│ ├── 37_Teams_home_screen.png
│ ├── 38_Team_created.png
│ ├── 39_Members_added.png
│ ├── 40_Message_visible_Teams_chat.png
│ ├── 41_SharePoint_home_page.png
│ ├── 42_New_site_created.png
│ └── 43_File_visible_SharePoint_document_library.png
└── LICENSE


---

## 👤 Author

<p align="center">
  <b>Oupa Simango</b> 🚀<br>
  <i>IT Support · System Administrator · Cloud Enthusiast</i>
</p>

<p align="center">
  <a href="https://github.com/yourusername">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
  <a href="https://linkedin.com/in/yourusername">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="mailto:your.email@example.com">
    <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
  </a>
</p>

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## ⭐ Show Your Support

<p align="center">
  <i>If you found this project helpful, please give it a ⭐ on GitHub!</i><br><br>
  <img src="https://img.shields.io/github/stars/yourusername/Enterprise-Hybrid-IT-Homelab?style=social" alt="Stars">
  <img src="https://img.shields.io/github/forks/yourusername/Enterprise-Hybrid-IT-Homelab?style=social" alt="Forks">
  <img src="https://img.shields.io/github/watchers/yourusername/Enterprise-Hybrid-IT-Homelab?style=social" alt="Watchers">
</p>

---

<p align="center">
  <b>Built with ❤️ in 2026</b>
</p>
