# Extend Emergency Calling with the Power Platform

| [Home](README.md) | [About](about.md) | [Deployment Guide](deployment.md) | [Support](support.md) | 
| --- | --- | --- | --- |

## Background
Emergency call notifications in Teams are a feature that allows administrators and users to receive alerts when someone in their organisation makes an emergency call using Teams Phone System. The notifications can help responders locate and assist the caller quickly and efficiently. Currently, this is limited to notifying a group of people in a group chat. 

This project was created to help Microsoft customers to  deliver emergency notifications through email, SMS and more. With the only limitation being Power Automate connectors. 

The core solution extends emergency notifications to email only, but you can tweek the Power Automate flow to utilise any Power Automate connector. [Check the list of connectors available for Power Automate](https://learn.microsoft.com/en-us/connectors/connector-reference/connector-reference-powerautomate-connectors) 


## Supporting Documentation
* Manage emergency calling policies in Microsoft Teams -  [link](https://learn.microsoft.com/en-us/MicrosoftTeams/manage-emergency-calling-policies)
* Network topology requirements - [link](https://learn.microsoft.com/en-US/microsoftteams/manage-your-network-topology)

## Support
If you encounter any bugs or issues while using the scripts, please raise them as issues [here](https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/issues) in this GitHub repository. You can also submit pull requests with your suggestions or improvements to the code. The project team appreciates your feedback and support. 

Thank you for using this project and I hope you find it useful and helpful. 😊

## Pre-requisites
### Core Solution:
* A **Service Account** with an appropriate license for:
  * Power Automate
  * Microsoft Teams
  * Microsoft Exchange
  * SharePoint
*	A SharePoint list (covered in the [Deployment Guide](deployment.md))
*	Teams Telephony Administrator, Teams Communication Administrator or Teams Administrator role.
* Emergency Calling Policy
* Network topology configured in Microsoft Teams

> [!NOTE]
  >  It's recommeded you use a Naming Convention with a static prefix to ensure all locations are captured, with a single string denoting the different locations, like a site reference.
   *(e.g. LOCATION SOUTHAMPTON)* 

   Find out more about the Network topology requirements [here](https://learn.microsoft.com/en-US/microsoftteams/manage-your-network-topology)

### Add-ons:
If you choose to extend your Emergency Calling notifications beyond just email, you may also need:
* An Azure Subscription
* Azure Communication Services
* 3rd Party Licenses
  [Check the list of connectors available for Power Automate](https://learn.microsoft.com/en-us/connectors/connector-reference/connector-reference-powerautomate-connectors)  

When extending further beyond the core solution, you can add more columns to the SharePoint list to hold different data for each site. 

E.g. a mobile number for SMS.  
<img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/930cc38f-a131-48c8-8e95-66e521115900" width="200" />


When making changes to the Power Automate Flow, open all conditions and Apply to each and place any extra action beneath the "Send an email (V2)" action.  
<img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/e81e534f-a0bf-4dcf-a2fc-6067178ddb82" width="200" />


Select the column you created as the "To:" address, and it's best to use the SiteSearch variable for the content, as this has been converted to plain text. (You may see that an Apply to each action is created, don't panic! This is normal)  
<img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/647d9206-184f-46d7-96a2-2cdc379e081d" width="200" />



 > [!NOTE]
  >  Be sure to use the [Unmanaged Solution](ExtendEmergencyCallingNotifications_unmanaged.zip)  if you are looking to make changes to the solution.  
  >  If you choose to use Power Automate premium connectors, you'll need to license these too or use a      Pay-as-you-go Power Platform plan. 
  [More information about PAYG.](https://learn.microsoft.com/en-us/power-platform/admin/pay-as-you-go-overview) 


## Disclaimer
> [!IMPORTANT]
> _These samples are provided "as is" without warranty of any kind. Microsoft further disclaims all implied warranties including without limitation any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the samples remains with you. In no event shall Microsoft or its suppliers be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the samples, even if Microsoft has been advised of the possibility of such damages. Because some states do not allow the exclusion or limitation of liability for consequential or incidental damages, the above limitation may not apply to you._

## Page info

| Name | README.md |
| :--- | :--- |
| Author | Rob Watts ([@robwatts365](https://github.com/robwatts365)) |
| **Version** | 1.0 |
| **Date** | 17/06/2024 |
