# Configure endpoint protection

* An endpoint is an address exposed by your application, to enable others to communicate with the application.
* Defend application endpoints by placing filter controls/ rule sets on the network traffic that the endpoint receives
* Azure resources that can protect your endpoint:
   * [Azure Front Door](14-Configure%20Azure%20Front%20Door%20service%20as%20an%20Application%20Gateway.md): An entry point with WAF and capability to route traffic to the "best" environment
   * [Application Gateway (WAF)](15-Configure%20a%20Web%20Application%20Firewall%20(WAF)%20on%20Azure%20Application%20Gateway.md): "WAFs provide a basic level of security for web applications"
   * [Azure Firewall](12-Create%20and%20configure%20Azure%20Firewall.md)
        * Can even implement DMZ as a perimeter network in front of the application. The DMZ is a separate subnet with the firewall.
   * [Azure DDoS protection + CDN](19-Implement%20DDoS%20protection.md)
* Prevent direct internet access for VMs (such as proxies or firewalls)
* Implement an automated and gated CI/ CD pipeline
   * FTP and Web Deploy that allow multiple publish methods should have the unused endpoints disabled. 
   * For Azure Web Apps, SCM is the recommended endpoint. [SCM means Source Control Manager](https://azure.github.io/AppService/2021/03/03/Custom-domain-for-scm-site.html)
* Apply authentication to the endpoints


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)