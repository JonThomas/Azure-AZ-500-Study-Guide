# Create and configure Azure Firewall

* An Azure Firewall protects resources in a Virtual Network (VNet).
* Azure Firewall uses a static public IP address for your virtual network resources allowing outside firewalls to identify traffic originating from your virtual network
   * What are the implications of this??
* Azure Firewall provides most of the functionality you'd expect in traditional firewalls. It also leverages Microsoft threat intelligence to identify malicious IP addresses
* Azure Firewall Premium also includes TLS-inspection and IDPS (Intrusion Detection and Protection System)

## Azure firewall scenarios

[Azure firewall vs Application Gateway WAF](https://docs.microsoft.com/en-us/azure/architecture/example-scenario/gateway/firewall-application-gateway)

* Azure firewall must be used to filter non-http traffic
* Azure firewall also includes intrusion detection capabilities
* Use only firewall: When there are no web applications
* Use application gateway only: When there are only web applications
* Most common scenario: Use both Firewall and Application Gateway in parallell (traffic goes through firewall **OR** gateway): Application gateway to protect web applications and Azure Firewall to protect all other workloads and filter outbound traffic.
* Gateway in front of Firewall: All traffic goes though both servers, so incoming source IPs can be available for web applications (The firewall NAT's the traffic - on other words: Changes the IP address to an internal one)
* Rare scenario: Firewall in front of Application Gateway. Because Firewall doesn't decrypt HTTPS traffic

TODO: Filtering traffic using Firewall vs Network Security Groups??


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)