# Extend Emergency Calling with the Power Platform

| [Home](README.md) | [About](about.md) | [Deployment Guide](deployment.md) | [Support](support.md) | 
| --- | --- | --- | --- |

## Background
Emergency call notifications in Teams are a feature that allows administrators and users to receive alerts when someone in their organisation makes an emergency call using Teams Phone System. The notifications can help responders locate and assist the caller quickly and efficiently. Currently, this is limited to notifying a group of people in a group chat. 

This project was created to help Microsoft customers to  deliver emergency notifications through email, SMS and more. With the only limitation being Power Automate connectors. 

## Supporting Documentation
* Manage emergency calling policies in Microsoft Teams -  [link](https://learn.microsoft.com/en-us/MicrosoftTeams/manage-emergency-calling-policies)

## Support
If you encounter any bugs or issues while using the scripts, please raise them as issues [here](https://github.com/robwatts365/ExtendEmergencyCalling/issues) in this GitHub repository. You can also submit pull requests with your suggestions or improvements to the code. The project team appreciates your feedback and support. 

Thank you for using this project and I hope you find it useful and helpful. 😊

## Pre-requisites
### Core Solution:
* A **Service Account** with the an appropriate license for:
  * Power Automate
  * Microsoft Teams
  * Microsoft Exchange
  * SharePoint
*	A SharePoint list (covered in the Deployment Guide 👇)
*	Teams Communication Administrator or Teams Administrator role.
* Emergency Calling Policy
* Network topology configured in Microsoft Teams
   > [!NOTE]
  >  It's recommeded you use a Naming Convention with a static prefix to ensure all locations are captured, with a single string denoting the different locations, like a site reference.
   *(e.g. CONTOSO SOUTHAMPTON)* 

### Add-ons:
If you choose to extend your Emergency Calling notifications beyond just email, you may also need:
* An Azure Subscription
* Azure Communication Services
* 3rd Party Licenses
  [Check the list of connectors available for Power Automate](https://learn.microsoft.com/en-us/connectors/connector-reference/connector-reference-powerautomate-connectors) 

 > [!NOTE]
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
| **Date** | 22/04/2024 |