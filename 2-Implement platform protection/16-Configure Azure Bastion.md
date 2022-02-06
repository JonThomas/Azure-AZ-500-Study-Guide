# Configure Azure Bastion

[Configure Azure Bastion](https://www.youtube.com/watch?v=WElUQm02BTU&list=PLLasX02E8BPDT2Z2pdCHNCkENpcQWy5n6&index=79)

* Azure Bastion is used instead of RDP'ing or SSH'ing directly into an Azure VM
* VMs are accessed and managed directly from within the Azure Portal
   * RDP packets never leave Azure
   * VM is always accessed using a private IP, never any public IPs.
* Microsoft recommends Azure Bastion whenever you have a VM that you need to log in to.
* Azure Bastion is a fully managed service in your virtual network in Azure
   * Your VM doesn't have to expose any public IPs to the internet
* Once Azure Bastion is deployed, any VM in the VNet can be accessed
* Internally Azure Bastion is a VM Scale Set, that can resize itself, and runs a set of applications and daemons

## Configuration

[Create Bastion](https://docs.microsoft.com/en-us/azure/bastion/tutorial-create-host-portal)

[Connect to Windows VM](https://docs.microsoft.com/en-us/azure/bastion/bastion-connect-vm-rdp)

[Connect to Linux VM](https://docs.microsoft.com/en-us/azure/bastion/bastion-connect-vm-ssh)

* The VNet must contain a subnet called "AzureBastionSubnet" where the Bastion host will be deployed
   * The Bastion subnet must be at least /27 or larger ([See Create a Virtual Network Gateway for subnet info](10-Secure%20the%20connectivity%20of%20virtual%20networks%20(VPN%20authentication,%20Express%20Route%20encryption).md#vpn))
* The Bastion host also need a public IP address, for some reason
* To use Azure Bastion, your user must have at least a Reader role on the VM, the VM's private NIC, and on the Azure Bastion resource
* A Windows VM must have port 3389 open for inbound traffic, to be able to connect
* A Linux VM must have port 22 open for inbound traffic
* A Linux VM can be accessed using:
   * Username/ password
   * Username and SSH private key
* A Windows VM can only be accessed using RDP. A Linux VM can only be accessed using SSH.

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)