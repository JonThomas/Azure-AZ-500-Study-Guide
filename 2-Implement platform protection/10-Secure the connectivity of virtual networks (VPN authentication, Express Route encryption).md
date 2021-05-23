# Secure the connectivity of virtual networks (VPN authentication, Express Route encryption)

* Azure Virtual Network (VNet) ~ segmented vLAN 
* A VNet enables Azure resources to securely communicate with each other, the internet, and on-premises networks. It also enables filtering of network traffic by deploying for example a firewall, routing of network traffic, and integration with Azure services.
* VNet is one of three ways Azure resources can communicate securely with each other:
   * VNet: Many types of Azure resources can be deployed into a VNet, including App Service, AKS and VM Scale Sets.
   * [Virtual Network Service Endpoints](18-Implement%20Service%20Endpoints.md)
   * [VNet Peering](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-peering-overview) - which is a way to connect multiple VNets
* All resources in a VNet can communicate outwards with other internet resources by default
   * Use a Load Balancer to restrict outbound traffic
* Add services (for example Microsoft.Sql or Microsoft.CognitiveServices) to the VNet in one of three ways:
   * Deploying a dedicated instance of the service
   * Using a Private link to an instance of a service from within the VNet
   * Connecting the VNet to the Service endpoint provided by a service
* A VNet can have at the most two Virtual Network Gateways: A VPN gateway and an Express Route gateway.
* Using VNets is free.

![Azure Segmented Network](img/SegmentedNetwork.png | width=100))

Figure: Azure VNet in relationship with other Network components

## VPN

Set up a VPN tunnel from an existing Azure VNet to an on-site location, or between two VNets in Azure, by using the following steps:

[Reference](https://docs.microsoft.com/en-us/azure/vpn-gateway/tutorial-site-to-site-portal)

1. Create a Virtual Network Gateway for the VNet in Azure. A gateway is the software VPN device for your Azure virtual network.
   1. The VPN Gateway requires a subnet that takes up some of the IP-addresses reserved by the VNet. Two or more virtual machines are deployed to the Gateway subnet. The VMs aren't directly configurable. They contain routing tables and specific gateway services.
   1. Microsoft recommends that the gateway subnet uses a /27 or /28, meaning that 27 or 28 out of the 32 bits in the IP address is used for network, and the other 5 or 4 bits are used for hosts (allowing 32 or 16 hosts in the VPN Gateway subnet, respectively). [Reference](https://www.freecodecamp.org/news/subnet-cheat-sheet-24-subnet-mask-30-26-27-29-and-other-ip-address-cidr-network-references/)
   1. A public IP address can be automatically created.
1. Create an Azure Local Network Gateway, representing the on-site location.
    1. Associate the on-site IP-adresse or DNS name (Fully qualified domain name = FQDN) with the local network gateway.
1. Configure the on-site VPN device, including setting up a string that will function as a shared key
1. Create an Azure VPN connection 
    1. Select the *VPN Gateway* -> Connections -> Add
    1. Select *site-to-site* since this is a VPN connection to a site different than Azure (instead of Express Route or VNet to VNet)
    1. Specify the shared key

### Enable MFA for VPN

 * Multi factor authentiation can be set up for the VPN connection.

[Reference](https://docs.microsoft.com/en-us/azure/vpn-gateway/openvpn-azure-ad-mfa)

## Express route

* Bypass the Internet entirely with a private Azure ExpressRoute connection
* ExpressRoute allows more reliable connections, faster speeds, consistent latencies, and higher security than typical connections over the Internet.
* Use a Virtual Gateway to set up Express route, a lot like setting up a VPN connection
   * The Virtual Gateway offers Basic, Standard and High Performance SKUs. Only Standard and High SKUs are supported with Express Route.

[Reference](https://docs.microsoft.com/en-us/azure/expressroute/expressroute-introduction)

![Express route](img/ExpressRoute.png)

Figure: Express route connections don't go over the public internet.

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)