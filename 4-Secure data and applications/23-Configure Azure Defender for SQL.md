# Configure Azure Defender for SQL

## Azure SQL Database Advanced Threat Protection

[SQL Advanced Threat Protection](https://docs.microsoft.com/en-us/azure/azure-sql/database/threat-detection-overview)

* Users can receive alerts upon
   * Injection attempts
   * Malicious login attempts
   * "Suspicious db activities"!?

[Advanced Threat Protection alerts](https://docs.microsoft.com/en-us/azure/security-center/alerts-reference#alerts-sql-db-and-warehouse)

Alerts:
* A possible vulnerability to SQL Injection (Medium): An application has submitted a faulty SQL statement
* Attempted logon by a potentially harmful application (High)
* Log on from an unusual Azure Data Center/ Location/ IP (Low/ Medium/ Medium)
* Login from a principal user not seen in 60 days: A principal user has logged in for the first time in 60 days (Medium)
* Potential SQL Brute Force attempt: An abnormally high number of failed sign in attempts (High)
* Potential SQL injection (High)
* Potentially Unsafe Action (High)
* Suspected brute force attack using a valid user (High)
* Suspected successful brute force attack (High): Success!
* Unusual export location: Someone has extracted a massive amoun of data from SQL Server

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)/