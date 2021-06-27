# Configure and monitor system updates for VMs

[Update Management overview](https://docs.microsoft.com/en-us/azure/automation/update-management/overview)

* "Update Management" in Azure Automation can be used to keep Windows and Linux VMs updated, both on-prem and in many clouds
* Can easily view available updates and manage process for installing updates
   * Example: Have Critical and Security patches install automatically 
* Update Management must be enabled and deployed to indiviual VMs
* Update Management requires:
   * A log analytics workspace linked to log update assessments and deployment results
      * The Log Analytics workspace has to be connected to the Automation Account
      * The Log Analytics agent has to be configured to report to the Log Analycs Workspace
   * Hybrid Runbook Worker - installed on the VM. Checks for maintenance window and starts updates
   * PowerShell DSC, and a public or private update repository for Linux VMs
   * Microsoft Update for Windows VMs
* Machines in multiple subscriptions within a tenant can be managed by Update Management.
   * Use Azure Lighthouse to manage machines in multiple tenants
* A deployment schedule decides when a machine, a Computer Group, or machines based on an Azure Query is updated
   * 20 minutes of the maintenance windows is reserved for reboot. If the update finishes with less than 20 minutes left, the reboot isn't performed.

## Automation accounts and Runbooks

[An introduction to Azure Automation](https://docs.microsoft.com/en-us/azure/automation/automation-intro)

* "Azure Automation delivers a cloud-based automation and configuration service that supports consistent management" of Azure environments.
   * Process automation
   * Update management
   * Configuration management
* Automation can be used for deployment, operations and decommissioning of resources
* A Runbook is a workflow
* Runbooks can be graphical
* Runbooks generate PowerShell code that is run by Automation workers
* Runbooks can be imported from the Runbook Gallery

TODO: How to update on-prem resources

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)