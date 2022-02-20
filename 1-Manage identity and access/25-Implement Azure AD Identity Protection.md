# Implement Azure AD Identity Protection

[Implement Azure AD Identity Protection](https://docs.microsoft.com/en-us/azure/active-directory/identity-protection/)

Keyword: RISK!

* Azure AD Identity Protection automates and remedies identity-based risk detection
   * "Users at risk"-email  
* User and Sign-in risks: 
   * User risk: The probability that a given identity or account is compromised.
   * Sign-in risk: The probability that a given authentication request isn't authorized by the identity owner.
* Three risk levels: low, medium, and high.
* Risk detection is only generated with correct credentials are used
* Three reports are provided
   * Risky users
   * Risky sign-ins
   * Risk detections

## Sign-in risk (the probability that a authentication request is compromised)
* Calculated in real time, or offline
* Sign-in risks that Azure AD identifies:
   * Anonymous IP address (Tor or anonymized VPN)
   * Atypical travel
   * Malware linked IP address
   * Unfamiliar sign-in location
   * Password spray
   * Azure AD threat intelligence (detects sign-in activity consistent with known attack patterns)

## User risk (the probability that the user is compromised)
* Calculated offline
* User risks that Azure AD can identify:
   * Leaked credentials
   * Azure AD threat intelligence (detects user activity consistent with known attack patterns)

## Identity protection in Azure Portal

* Investigate risks using the Identity protection dashboard in Azure that displays trends of new risky users and risky sign-ins
   * Tiles can be added to the dashboard to display for example Legacy authentication or Identity secure score
* Risk data can be exported for further analysis

## Security tips
* Make users sign up for [Self Service Password Reset (SSPR)](13-Manage%20Azure%20AD%20users.md) and MFA.
* Both features can be enabled at the same time, for an improved user sign-up experience, using [Combined registration](https://docs.microsoft.com/en-us/azure/active-directory/authentication/howto-registration-mfa-sspr-combined)

## TODO
* Two modes: Enabled and Assigned risks?


Identity Protection is a feature of Azure AD Premium P2.

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)