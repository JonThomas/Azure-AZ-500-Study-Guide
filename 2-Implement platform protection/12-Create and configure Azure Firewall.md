# Create and configure Azure Firewall

[Create and configure Azure Firewall](https://docs.microsoft.com/en-us/azure/firewall/features)

[Azure Firewall Features](https://docs.microsoft.com/en-us/azure/firewall/features)

* An Azure Firewall protects resources in a Virtual Network (VNet).
   * Each virtual network can have a firewall enabled
   * A subnet called AzureFirewallSubnet is required in the VNet, consisting of at least 64 addresses (10.0.0.0/26, or smaller)
* Azure Firewall uses a static public IP address for your virtual network resources allowing outside firewalls to identify traffic originating from your virtual network
   * At least one (and up to 250) public IP addresses must be configured on the firewall
* Azure Firewall provides most of the functionality you'd expect in traditional firewalls. It also leverages Microsoft threat intelligence to identify malicious IP addresses
* Azure Firewall Premium also includes TLS-inspection and IDPS (Intrusion Detection and Protection System)
* Firewall rules
   * Application rules: Allows the subnet to access a fully qualified domain name (FQDN)
   * Network rules: Allows definition of source/ destination IP addresses, ports and protocol

## Azure firewall/ Application Gateway scenarios

[Azure firewall vs Application Gateway WAF](https://docs.microsoft.com/en-us/azure/architecture/example-scenario/gateway/firewall-application-gateway)

* Azure firewall must be used to filter non-http traffic
* Azure firewall also includes intrusion detection capabilities
* Use only firewall: When there are no web applications
* Use application gateway only: When there are only web applications
* Most common scenario: Use both Firewall and Application Gateway in parallell (traffic goes through firewall **OR** gateway): Application gateway will protect web applications and Azure Firewall protects all other workloads and filters outbound traffic.
* Gateway in front of Firewall: All traffic goes though both servers, so incoming source IPs can be available for web applications (The firewall NAT's the traffic - in other words: changes the IP address to an internal one)
* Rare scenario: Firewall in front of Application Gateway. Because Firewall doesn't decrypt HTTPS traffic


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)