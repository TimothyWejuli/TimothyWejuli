# Hi, I'm Timothy Wejuli

I'm an aspiring System Administrator and Cloud Engineer. I build hands-on labs focused on Windows Server administration, Active Directory Domain Services (AD DS), ServiceNow ITSM workflows, and PowerShell automation.

## Projects

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
