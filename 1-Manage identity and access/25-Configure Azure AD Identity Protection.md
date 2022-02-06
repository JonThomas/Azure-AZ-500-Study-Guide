# Configure Azure AD Identity Protection

[Configure Azure AD Identity Protection](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/)

Keyword: RISK!

* Automate risk detection
   * "Users at risk"-email  
* Investigate risks using the Identity protection dashboard in Azure that displays trends of new risky users and risky sign-ins
   * Tiles can be added to the dashboard to display for example Legacy authentication or Identity secure score
* Export risk data for further analysis
* Risk types that can be detected:
   * Anonymous or malware linked IP addresses
   * Atypical travel
   * Leaked credentials
   * ...
* Three risk levels: low, medium, and high.

## Security tips
* Make users sign up for [Self Service Password Reset (SSPR)](13-Manage%20Azure%20AD%20users.md) and MFA.
* Both features can be enabled at the same time, for an improved user sign-up experience, using [Combined registration](https://docs.microsoft.com/en-us/azure/active-directory/authentication/howto-registration-mfa-sspr-combined)


[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)