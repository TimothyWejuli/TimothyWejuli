# Hi, I'm Timothy Wejuli

**System Administration | Cloud Engineering | Infrastructure as Code**

I deploy, secure, and troubleshoot Azure infrastructure with Terraform, and I administer Windows Server, Active Directory, and Linux environments. Each project below starts with a real business problem, is built hands-on from zero, and documents what broke and how I fixed it. My work covers access control (RBAC), patch management, security monitoring with a SIEM, ServiceNow ITSM workflows, and PowerShell automation.

## Infrastructure as Code and Cloud Labs

Azure environments deployed and managed with Terraform, focused on access control, security, cost governance, and patch management.

### Virtual Machines and RBAC (Azure + Terraform)

[View the project repository](https://github.com/TimothyWejuli/Virtual-Machines-and-RBAC)

| Focus | Tools and technologies |
| --- | --- |
| Deploy a Linux VM with network, subnet, and NIC | Terraform, `azurerm` provider |
| Encrypt the OS disk with a customer-managed key | Azure Key Vault, disk encryption set |
| Create a custom role limited to reading and restarting one VM | Azure RBAC, custom role definitions |
| Scope the role assignment to a single resource | Role assignments, VM scope |
| Require a `CostCenter` tag on resources | Azure Policy |
| Set a monthly cost budget with an 80% alert | Azure Cost Management budgets |
| Troubleshoot SKU capacity, hypervisor generation, and state errors | Azure CLI, `terraform plan` / `apply` / `destroy` |

### NTFS File Server Lab (Azure + Terraform)

[View the project repository](https://github.com/TimothyWejuli/ntfs-lab-terraform)

| Focus | Tools and technologies |
| --- | --- |
| Deploy a domain controller, file server, and Windows 11 client | Terraform, `azurerm` provider |
| Store the admin password and Terraform state securely | Azure Key Vault, Azure Blob Storage remote state |
| Create OUs, security groups, and test users | Active Directory, PowerShell |
| Create SMB shares on the file server | `New-SmbShare`, SMB |
| Apply NTFS permissions per department group | `icacls`, NTFS inheritance |
| Configure VMs without RDP | Azure CLI, `az vm run-command` |
| Join servers and a client to the domain and allow RDP with Group Policy | AD DS, DNS, Group Policy |
| Verify access as five test users and troubleshoot errors | `whoami`, `nslookup`, `Get-ChildItem`, `New-Item` |

### Azure RBAC Access Control Lab (Azure + Terraform)

[View the project repository](https://github.com/TimothyWejuli/azure-rbac-lab-terraform)

| Focus | Tools and technologies |
| --- | --- |
| Assign Owner, Virtual Machine Contributor, and Reader roles scoped to one VM | Azure RBAC, Terraform `azurerm_role_assignment` |
| Read existing infrastructure instead of recreating it | Terraform data sources |
| Keep this lab's state separate from Part 1 | Azure Blob Storage remote state, separate state key |
| Look up Microsoft Entra ID Object IDs for test users | Azure CLI, PowerShell |
| Validate live role assignments and export a report | PowerShell, `az role assignment list` |
| Prove least privilege by signing in as each persona | Azure CLI, `AuthorizationFailed` testing |

### Azure Update Manager Patch Management Lab (Azure + Terraform)

[View the project repository](https://github.com/TimothyWejuli/azure-update-manager-lab)

**Business problem:** Unpatched servers are a leading cause of security incidents. At scale, the hard part is knowing which machines are missing which patches, enforcing a consistent schedule, and proving compliance to auditors. This lab replaces the WSUS model with a cloud-native patch pipeline built from zero in Terraform.

| Focus | Tools and technologies |
| --- | --- |
| Deploy a domain controller and two domain-joined servers | Terraform modules, `azurerm` provider, AD DS, DNS |
| Enroll VMs automatically in periodic patch assessment | Azure Policy, managed identity |
| Schedule a weekly patch window for Critical, Security, and UpdateRollup updates | Azure Update Manager, maintenance configurations |
| Assign the schedule to each VM with platform patch orchestration | `AutomaticByPlatform` patch mode, maintenance assignments |
| Run on-demand assessments and find missing updates (4 per server) | Update Manager, `az vm assess-patches` |
| Validate compliance and export an audit report | PowerShell, `Invoke-AzVMPatchAssessment`, JSON |
| Troubleshoot vCPU quota limits and VM delete errors | Azure CLI, `terraform plan` / `apply` / `destroy` |

## System Administration and Security Labs

Hands-on administration of Windows Server, Active Directory, Linux, and security monitoring tools.

### SIEM Home Lab: Endpoint Detection and Security Monitoring

[View the project repository](https://github.com/TimothyWejuli/siem-home-lab)

**Business problem:** Most breaches leave evidence in logs, like a new admin account nobody requested or a run of failed logons, but those logs sit on individual machines where nobody reads them. This lab builds a central security monitoring pipeline from zero with open-source tools, so suspicious activity triggers an alert instead of being found weeks later.

| Focus | Tools and technologies |
| --- | --- |
| Build a SIEM server on a Linux VM | Ubuntu Server 24.04, VirtualBox, Wazuh 4.14 (indexer, manager, dashboard) |
| Fix VM networking so endpoints can reach the SIEM | Bridged adapter, `ip a`, `Test-NetConnection` |
| Administer the server remotely | OpenSSH, PowerShell SSH client, `systemctl` |
| Enroll a Windows endpoint and forward Security event logs | Wazuh agent, `ossec.conf`, `agent-auth.exe`, `NET START WAZUH` |
| Simulate attacker account activity and confirm detections | Event IDs 4720, 4732, 4625, 4726, `net user`, `net localgroup` |
| Triage alerts by severity and review their MITRE ATT&CK technique tags | Wazuh rules, DQL queries, T1136.001, T1098, T1110, T1531 |
| Review baseline security posture | CIS benchmark (SCA), vulnerability detection |
| Troubleshoot virtualization, networking, SSH, and agent enrollment | UEFI SVM mode, port tests on 1514/1515, manual agent enrollment |

### Active Directory Domain Lab (Azure)

[View the project repository](https://github.com/TimothyWejuli/Active-Directory-Lab)

| Focus | Tools and technologies |
| --- | --- |
| Promote a Windows Server to a domain controller | Server Manager, AD DS, DNS |
| Create organizational units (OUs) | Active Directory Users and Computers, PowerShell |
| Create users, groups, and group memberships | `New-ADUser`, `New-ADGroup`, `Add-ADGroupMember` |
| Configure Group Policy Objects (GPOs) | Group Policy Management Console |
| Configure role-based access with security groups | Active Directory security groups |
| Reset passwords and manage account lifecycles | `Set-ADAccountPassword`, `Disable-ADAccount`, `Enable-ADAccount` |
