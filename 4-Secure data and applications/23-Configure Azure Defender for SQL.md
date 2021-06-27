# Configure Azure Defender for SQL

## Azure SQL Database Advanced Threat Protection

[SQL Advanced Threat Protection](https://docs.microsoft.com/en-us/azure/azure-sql/database/threat-detection-overview)

* Users can receive alerts upon
   * Injection attempts
   * Malicious login attempts
   * "Suspicious db activities"!?

[Advanced Threat Protection alerts](https://docs.microsoft.com/en-us/azure/security-center/alerts-reference#alerts-sql-db-and-warehouse)

## Alerts

### High Severity

* Attempted logon by a potentially harmful application
* Potential SQL Brute Force attempt: An abnormally high number of failed sign in attempts
* Potential SQL injection
* Suspected brute force attack using a valid user
* Suspected successful brute force attack: Success!
* Potentially Unsafe Action
* Unusual export location: Someone has extracted a massive amount of data from SQL Server

### Medium Severity

* A possible vulnerability to SQL Injection: An application has submitted a faulty SQL statement
* Log on from an unusual Location/ IP
* Login from a principal user not seen in 60 days: A principal user has logged in for the first time in 60 days

### Low Severity

* Log on from an unusual Azure Data Center

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)/