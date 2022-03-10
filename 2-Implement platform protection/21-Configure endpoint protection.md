# Configure endpoint protection

[Configure endpoint protection](https://docs.microsoft.com/en-us/azure/architecture/framework/security/design-network-endpoints)

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

## Microsoft Defender for Endpoint

[What is Microsoft Defender for Endpoint](https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

* Microsoft Defender for Endpoint is an enterprise endpoint security platform to prevent, detect, investigate and respond to advanced threats
* Its a core part of Microsoft Defender, together with Defender for Office 365, Cloud App Security and Defender for Identity
> ### Is this still correct?
> * Operates within a tenant
>    * Data is only available through Azure AD.
>    * Sandbox for uploading files
* Accessible through Microsoft Defender Security Center

### 7 pillars:

1. Threat and vulnerability management
   * Risk based approach
   * Protects angainst vulnerabilities and misconfiguration in real time. 
   * Based on sensors
   * Prioritizes
1. Attack surface reduction
   * "Application Control" - allows only trusted applications to run
   * Rules to restict behaviour
   * Network protection - prevents apps from accessing dangerous locations
1. Next gen antivirus
1. Endpoint Detection for Endpoint & response - for finding threats that want to stay hidden
   * Collects behaviours and attacker techniques on endpoints to define an alert for suspicious or malicious activity
   * Visually investigate and take actions: Threat hunting
   * Write queries across all endpoints. Six months of data
   * Submit files for inspection, using the sandbox
1. Automation: Auto investigation and remediation
   * Reduces alerts that have to be manually handled
1. Mcrosoft Threat Experts
   * Managed threat service
   * Reach out to experts
1. Management & APIs


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)