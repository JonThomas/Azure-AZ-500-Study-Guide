# Configure diagnostic logging and log retention

[Azure AD activity logs in Azure Monitor](https://docs.microsoft.com/en-us/azure/active-directory/reports-monitoring/concept-activity-logs-azure-monitor)
[Enable and manage Azure Storage Analytics logs (classic)](https://docs.microsoft.com/en-us/azure/storage/common/manage-storage-analytics-logs?tabs=azure-portal)

## Different logs

* AD - sign-in history and audit trail
   * Security reports
      * Users flagged for risk
      * Risky sign-ins
   * Activity reports
      * Audit logs
      * Sign-ins (how many sign-ins has been made last week/ What's the sign-in pattern of a user?)
* Activiy logs - logs from all resources for the management plan 
   * Activity logs for a VM will therefore provide information about changes being made to the VM in Azure (who created it) - not VM guest level diagnostics information (who turned the firewall off)
   * Stored in table AzureActivity
   * Available in the portal from most blades. The menu that you open it from determines the initial filter. 
* Resource logs - logs for all resources for the data plane
   * Resource logs aren't available until they're sent to a destination
* Storage account logs (Diagnostics logs are stored in the _$logs_ blob container)
   * Metrics: For each storage type (blob, file, table and queue), metrics can be kept - both minute and/ or hour resolution
   * Logs: For blob, table and queue (not file), logs kan be kept
      * Logs for read and/ or write and/ or delete operations kan be kept
   * Retention can be specified for both metrics and logs
   * Only logs with the v2 format can store requests authorized with an OAuth 2.0 token provided by Azure AD
* Diagnostics settings ("Logs")
   * Diagnostic logs for VMs must be activated: "Guest-level monitoring"

## Default retention

* Azure AD stores logs for 90 days by default
* Azure Acitvity logs are also stored for 90 days by default
* (Resource logs arent stored anywhere, until they're sent to a destination)

## Log destinations and retention

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