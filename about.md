# Extend Emergency Calling with the Power Platform

| [Home](README.md) | [About](about.md) | [Releases](https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/releases)| [Deployment Guide](deployment.md) | [Support](support.md) |
| --- | --- | --- | --- | --- |

## Overview
Emergency call notifications in Teams are a feature that allows administrators and users to receive alerts when someone in their organisation makes an emergency call using Teams Phone System. The notifications can help responders locate and assist the caller quickly and efficiently. Currently, this is limited to notifying a group of people in a group chat. 

This project was created to help Microsoft customers to  deliver emergency notifications through email, SMS and more. With the only limitation being Power Automate connectors. 

## Benefits
* Extend Emergency Call notifications beyond a Teams Group Chat, including:
  * Email 
  * SMS (through Azure Communication Service)
  * Using 3rd Party solutions, available as Power Automate connectors. 
* Deliver Emergency call notifications dynamically dependant on location. (or other criteria)

## How it works

The core solution extends emergency notifications to email only, but you can tweek the Power Automate flow to utilise any Power Automate connector. [Check the list of connectors available for Power Automate](https://learn.microsoft.com/en-us/connectors/connector-reference/connector-reference-powerautomate-connectors) 

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



## Page info

| Page | About |
| :--- | :--- |
| Author | Rob Watts ([@robwatts365](https://github.com/robwatts365)) |
| **Version** | 1.0 |
| **Date** | 17/06/2024 |



