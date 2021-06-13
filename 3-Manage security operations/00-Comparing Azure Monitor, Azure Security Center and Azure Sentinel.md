# Comparing Azure Monitor, Azure Security Center and Azure Sentinel

[Azure Sentinel, Azure Monitor, Azure Security Center and Log Analytics Relations](https://www.eshlomo.us/azure-security-sentinel-monitor-relation/)

## Log Analytics

* A huge logging platform that can collect records from multiple log sources regardless of physical location, including workloads, services and servers.
* Provides users with the ability to query, analyze and correlate logs.
   * Uses custom query language.
* Backbone of all other monitoring services

## Azure Monitor

* Complete solution for collecting, analyzing and acting on telemetry from Azure, other cloud providers and on-premise environments.
* Components
   * Alerting
   * Action Groups
   * Action Rules
* Features:
   * Application Insights
       * Create smart alerts
   * Automate actions
      * Azure Function
      * Azure Logic Apps
      * ...
   * Azure dashboards and workbooks can create visualizations

### Monitoring agent

[Azure Monitor agent overview](https://docs.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-overview)

* Collects logs from guest operating system of VMs, and feeds them to Azure Monitor.
* Centrally configured
* Set up Data Collection Rules (DCR) to configure data collection from each agent.
   * Rules can be defined once, and resued by many agents.
* Replaces Log Analytics agent, Diagnostics extensions and Telegraf agent.


# Azure Security Center

* Provides insight into the security state across your cloud
* Features:
   * Threat analysis
   * Provides security recommendations and remediation actions
   * Compliance audits


[Return to Manage security operations](README.md)

[Return to Table of Contents](../README.md)