# Deployment Guide

| [Home](README.md) | [About](about.md) | [Deployment Guide](deployment.md) | [Support](support.md) | 
| --- | --- | --- | --- |

## 1. Pre-requisites
### Core Solution:
* A **Service Account** with the an appropriate license for:
  * Power Automate
  * Microsoft Teams
  * Microsoft Exchange
  * SharePoint Online
  
*	A SharePoint list (covered further down 👇)
* A Power Platform environment with Dataverse enabled
*	Teams Communication Administrator or Teams Administrator role.
* Emergency Calling Policy
* Network topology configured in Microsoft Teams
  
> [!NOTE]
  >  You should use a naming convention with a static prefix to ensure all locations are captured, with a single string denoting the different locations, like a site reference.
  [PREFIX] [LOCATION IDENTIFIER] 
  *(e.g. **CONTOSO** SOUTHAMPTON)* 

Find out more about the Network topology requirements [here](https://learn.microsoft.com/en-US/microsoftteams/manage-your-network-topology)

### Add-ons:
If you choose to extend your Emergency Calling notifications beyond just email, you may also need:
* An Azure Subscription
* Azure Communication Services
* 3rd Party Licenses
  [Check the list of connectors available for Power Automate](https://learn.microsoft.com/en-us/connectors/connector-reference/connector-reference-powerautomate-connectors) 

 > [!NOTE]
  >  If you choose to use Power Automate premium connectors, you'll need to license these too or use a      Pay-as-you-go Power Platform plan. 
  [More information about PAYG.](https://learn.microsoft.com/en-us/power-platform/admin/pay-as-you-go-overview) 


## 2. Configuration

### Create SharePoint List

The first thing you'll need to decide is where to host the SharePoint list holding the data for this solution. 

For the purpose of this guide, I have created a new Team in Microsoft Teams called Emergency Notifications, and I will use this SharePoint site to host my SharePoint list.  

1) Navigate to the SharePoint site you have chosen to host the SharePoint list. 
2) Click the "+ New" button.
    ![image](https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/e5992819-a9a5-4944-9fe8-f7d453cf5376)
4) Select "Blank List".
5) Give your list an appropriate name (I'm using SiteList)
6) Once created, click the gear in the top right hand corner, and select List settings.
7) Under Columns, select the "Title" column.
8) Rename the column's name to "SiteRef".
9) Toggle "Require that this column contains information" to Yes. 
10) Toggle "	Enforce unique values" to Yes.
11) Press OK in the bottom right corner of the window. 
12) Click "Create column".
13) Name the column "Email".
14) Toggle "Require that this column contains information" to Yes. 
15) Press OK in the bottom right corner of the window. 
    



## Page info

| Page | Deployment Guide |
| :--- | :--- |
| Author | Rob Watts ([@robwatts365](https://github.com/robwatts365)) |
| **Version** | 1.0 |
| **Date** | 22/04/2024 |
