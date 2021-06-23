# Create and manage Shared Access Signatures (SAS)

## Shared Access Signatures

[Grant limited access to Azure Storage resources using shared access signatures (SAS)](https://docs.microsoft.com/en-us/azure/storage/common/storage-sas-overview)

* A Shared access signature (SAS) is a URI that points to one or more resources. The URI contains a token, that includes a set of query parameters indicating how resources can be accessed
* Three types of Shared Access Signatures
   * User delegation SAS 
      * Blob storage only
      * Secured with Azure AD credentials
      * _Preferred over Service/ Account SAS_
   * Service SAS
      * Delegates access to only one storage service (Blob, Queue, Table or Files)
      * Supports _Stored Access Policy_, that gives option to revoke permissions without having to regenerate storage account keys
      * Signed with the storage account key (shared key than must be stored with client code)
   * Account SAS
      * Delegates access to one or more storage services, as well as some service-level operations and some extra CRUD operations
      * Signed with the storage account key (shared key than must be stored with client code)
* Generation of SAS' can be generated on the client side, and can't be audited
* Use a SAS to give resource access to a client who does not othervice have permission, for example when uploading/ downloading large amounts of data and direct storage access if preferrable over having a server in front of the storage.

![Shared access signature (SAS)](img/SharedAccessSignature.png)

## Shared Access Policy (= Stored access policy)
* Attach a Shared/ Stored Access Policy to the Shared Access Signarure to limit access to the resource in time etc.
* The SAS inherits the constraints of the Shared Access Policy
* A Shared Access Policy can be changed, and thus revoke the SAS

## Security recommendations

* Use HTTPS to create and distribute a SAS
* Prefer User delegation SAS
* Have a revocation plan for a SAS, in case it is compromised
* Define a Stored access policy for a Service SAS
* Define short expirations times
* Validate data written by a SAS after it's written, but before it's access by the application
* Use Azure Monitor and Azure Storage logs to monitor (spikes in) authentication failures

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)