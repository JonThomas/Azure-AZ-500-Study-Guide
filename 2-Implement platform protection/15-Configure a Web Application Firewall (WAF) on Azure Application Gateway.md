# Configure a Web Application Firewall (WAF) on Azure Application Gateway

* Web Application Firewall provides protection against SQL injection, XSS, and many other exploits
* WAF on Application Gateway is based on OWASP Core Rule Set (CRS)
* Protects only HTTP-based resources (hence the name: *Web Application* Firewall)
* WAF modes:
   * Detection mode (log only)
   * Prevension mode (block requests). Attackers receive a 403 Unauthorized Access, and the request is logged
      * Traditional mode (rules are evaluated independently)
      * Anomality Scoring mode (Rules have score, and request is only blocked if the score >= 5). Default for OWASP 3.x

## Benefits of WAF on Application Gateway

* Application Gateway can host up to 40 websites, that will all be protected by the WAF
* Possible to create custom policies for each site
* Monitor attacks using real time WAF log, integrated into [Azure Monitor](../3-Manage%20security%20operations/README.md#monitor-security-by-using-azure-monitor)
* WAF is also integrated in Security Center

## Policies and rules

* A policy is a collection of Azure-managed rules, custom rules and exceptions
* Policies on an Application Gateway exist on a global, per-site or per-url level.
* Custom rules are processed first
* A rule consits of:
   * A match condition
   * A priority (Unique integer - small number have higher priority)
   * An action (ALLOW/ BLOCK/ LOG)

TODO: [Create an application gateway with a Web Application Firewall](https://docs.microsoft.com/en-us/azure/web-application-firewall/ag/application-gateway-web-application-firewall-portal)

![WAF Monitoring](img/WAFMonitoring.png)

Figure: WAF Monitoring, with Security Center and Azure Monitor

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)