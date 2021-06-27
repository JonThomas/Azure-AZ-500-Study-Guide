# Configure diagnostic logging and log retention

[Azure AD activity logs in Azure Monitor](https://docs.microsoft.com/en-us/azure/active-directory/reports-monitoring/concept-activity-logs-azure-monitor)

## Platform logs

* AD - sign-in history and audit trail
* Activiy logs - logs from all resources for the management plan 
   * Stored in table AzureActivity
* Resource logs - logs for all resources for the data plane

## Default retention

* Azure AD stores logs for 90 days by default
* Azure Acitvity logs are also stored for 90 days by default

## Increase log retention

* Logs can be sent to different destinations for longer retention by creating a diagnostics setting
   * Log analytics workspace - to analyze them using Azure Monitor. Works across regions.
   * Event Hub - to forward the events to outside Azure, or to be consumed by other services like Azure Stream Analytics or Azure Functions
      * Cannot configure retention in Even Hub??
      * The event hub and the resource that logs must be in the same region.
   * Storage - for archiving. The storage account must be in the same region.
      * A delete lifecycle policy can be set up on the storage to specify log retention: [Expire data based on age](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-lifecycle-management-concepts?tabs=azure-portal#expire-data-based-on-age)

* Collecting logs across tenants requires Azure Lighthouse

[Return to Manage security operations](README.md)

[Return to Table of Contents](../README.md)