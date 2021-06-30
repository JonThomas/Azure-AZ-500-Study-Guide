# Configure Just in Time VM access by using Azure Security Center

* Can be set up with Network Security Group or Azure Firewall

## Process

1. Enable JIT on your VM, using Security Center or programmatically
   * Inboud traffic is now locked down by a rule in the NSG/ Firewall
   * Access can be limited to RDP, SSH and/ or WinRM (other custom ports can be added)
1. Request access to VM using Security Center (or an Azure VM, PowerShell or by using a REST API)
   * Access is granted for three hours
1. Audit JIT access

[Return to Manage security operations](README.md)

[Return to Table of Contents](../README.md)