# Configure and monitor system updates for VMs

* "Update Management" in Azure Automation can be used to keep Windows and Linux VMs updated, both on-prem and in many clouds
* Can easily view available updates and manage process for installing updates
   * Example: Have Critical and Security patches install automatically 
* Update Management must be enabled and deployed to indiviual VMs
* Update Management requires:
   * A log analytics workspace
   * Hybrid Runbook Worker - installed on the VM. Checks for maintenance window and starts updates
   * PowerShell DSC, and a public or private update repository for Linux VMs
   * Microsoft Update for Windows VMs
* Machines in multiple subscriptions within a tenant can be managed by Update Management.
   * Use Azure Lighthouse to manage machines in multiple tenants
* A deployment schedule decides when a machine, a Computer Group, or machines based on an Azure Query is updated
   * 20 minutes of the maintenance windows is reserved for reboot. If the update finishes with less than 20 minutes left, the reboot isn't performed.

TODO: Automation account and key features
TODO: How to update on-prem resources

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)