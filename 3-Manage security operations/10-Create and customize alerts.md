# Create and customize alerts

[Create, view, and manage log alerts using Azure Monitor](https://docs.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-log)

## Create and view log alerts

* Alerts are set up by specifying Log Analytics Query that evaulates logs and can fire an alert based on the results.
* Alert rules have three components
   * Criteria (ex: CPU time > 5 seconds)
   * Target
   * Action
* The Criteria (Condition) relies on Signals from different sources:
   * Metrics (For example CPU time)
   * Platform logs 
      * Activity Logs (Administrative events, for example Delete firewall. Entries in the Activity Log are system generated and cannot be changed or deleted.)
      * Resource logs (Resource level)
      * AD logs (Tenant level)
   * Log search queries
* Alerts can be created on spesific resources, resource-groups or across many resources using the Monitor -> Alert functionality in the Azure portal

## Manage log alerts

[Overview of alerts in Microsoft Azure](https://docs.microsoft.com/en-us/azure/azure-monitor/alerts/alerts-overview)

* Alerts are available from Monitor -> Alerts in the portal
* Alert workflow
   * New -> Acknowledged -> Closed
   * States are changed manually or programatically
   * All workflow transitions are always available

[Return to Manage security operations](README.md)

[Return to Table of Contents](../README.md)