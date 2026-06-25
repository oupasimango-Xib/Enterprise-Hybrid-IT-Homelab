
Enterprise Hybrid IT Homelab (End-to-End Project)
🚀 Project Overview
This homelab simulates a real enterprise hybrid identity and device management environment, combining on-premises infrastructure with Microsoft 365 cloud services.


🏗️ Architecture
Virtual Machines

- DC01 (Domain Controller)
- CLIENT01 (Windows 11 Client)
Networking

- Adapter 1: Internal network (VM communication)
- Adapter 2: NAT/Internet access


⚙️ Phase 1: On-Premises Setup
✅ System & Network Setup
screenshots/00_System_Requirements.png screenshots/01_Vmware_Network_Adapters01.png screenshots/01_Vmware_Network_Adapters02.png screenshots/02_Network_Adapters_list.png
✅ Static IP Configuration
screenshots/03_Static_IP_Config.png
✅ Active Directory Installation
screenshots/04_ADDS_Installation01.png screenshots/04_ADDS_Installation02.png screenshots/05_Domain_Promotion.png screenshots/06_Verify_Domain.png
✅ OU + Users
screenshots/07_OU_Structure.png screenshots/8_AD_Users01.png screenshots/8_AD_Users02.png screenshots/8_AD_Users03.png
✅ User Properties
screenshots/09_User_Properties01.png screenshots/09_User_Properties02.png screenshots/09_User_Properties_LogonHours.png


��️ Phase 2: Domain Join
screenshots/10_Domain_Join01.png screenshots/10_Domain_Join02.png screenshots/10_Domain_Success.png
screenshots/14_Domain_Login.png


🌐 Phase 3: DHCP Configuration
screenshots/11_DHCP_Installed01.png screenshots/11_DHCP_Installed02.png screenshots/11_DHCP_Installed03.png
screenshots/12_DHCP_Scope.png screenshots/13_DHCP_Options.png


🔐 Phase 4: GPO Security
screenshots/15_GPO_Password_Policy.png


☁️ Phase 5: Microsoft 365 Setup
screenshots/16_M365_Admin_Dashboard.png screenshots/17_M365_Users.png screenshots/18_M365_Licenses.png


🔑 Phase 6: Identity & Entra ID
screenshots/19_Security_Defaults.png screenshots/20_SSPR_Config.png
screenshots/21_Download_MicrosoftEntra_connect.png screenshots/22_MicrosoftEntra_installation.png screenshots/23_MicrosoftEntra_Config.png screenshots/24_MicroEnta_Config.png
screenshots/25_Sync_Service.png screenshots/26_AzureAD_Users.png screenshots/27_AzureAD_User_Properties.png


💻 Phase 7: Device Enrollment (Intune)
screenshots/28_CLIENT01_Connect.png screenshots/29_Microsoft_Intune.png


��️ Phase 8: Intune Policies
screenshots/30_Policy_summary.png screenshots/31_Password_enforcement_configured.png screenshots/32_Compliance_policy_summary.png
screenshots/33_CLIENT01_Compliant.png screenshots/34_CLIENT01_Complient1.png screenshots/35_CLIENT01_Complient2.png


📧 Phase 9: Microsoft 365 Applications
screenshots/36_Inbox + sent email.png
✅ Microsoft Teams
screenshots/37_Teams home screen.png screenshots/38_Team created (IT Support Team).png screenshots/39_Members added.png screenshots/40_Message visible in Teams chat.png
✅ SharePoint
screenshots/41_SharePoint home page.png screenshots/42_New site created (IT Department Site).png screenshots/43_File visible in SharePoint document library.png


🎯 Skills Demonstrated

- Active Directory Administration
- Microsoft Entra ID (Hybrid Identity)
- Microsoft Intune (Device Management)
- Microsoft 365 Administration
- Networking (DHCP, DNS)
- Security (Conditional Access, Policies)
- Troubleshooting & IT Support


💡 Conclusion
This project demonstrates real-world enterprise IT operations including hybrid identity, device management, and cloud integration. It showcases hands-on skills applicable to IT Support and System Administrator roles.


🔗 Author
Built by: Oupa Simango 🚀
