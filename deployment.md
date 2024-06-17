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

### Creating the SharePoint List

The first thing you'll need to decide is where to host the SharePoint list holding the data for this solution. 

For the purpose of this guide, I have created a new Team in Microsoft Teams called Emergency Notifications, and I will use this SharePoint site to host my SharePoint list.  

1) Navigate to the SharePoint site you have chosen to host the SharePoint list. 
2) Click the "+ New" button.  
   <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/e5992819-a9a5-4944-9fe8-f7d453cf5376" width="200" />
3) Select "Blank List".  
   <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/009d7604-b870-4f02-9a45-a3be4b7723b7" width="200" />
4) Give your list an appropriate name (I'm using SiteList)
5) Once created, click the gear in the top right hand corner, and select List settings.  
   <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/7cedcfdc-5524-42b9-bc25-86579ca7d320" width="200" />
6) Under Columns, select the "Title" column.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/0667cb8c-d978-4067-91c7-cc38e73bacc4" width="200" />
7) Rename the column's name to "SiteRef".
8) Toggle "Require that this column contains information" to Yes. 
9) Toggle "	Enforce unique values" to Yes.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/ac1cfbec-8cbc-42b2-a2f1-cb1ac0c0aab2" width="200" />
10) Press OK in the bottom right corner of the window. 
11) Click "Create column".  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/e4518790-74ff-44a2-a11b-b3b773b9819e" width="200" />
12) Name the column "Email".
13) Toggle "Require that this column contains information" to Yes.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/a40e6ad8-b696-4c4e-94fe-7761b58832dc" width="200" />
14) Press OK in the bottom right corner of the window. 
    
### Deploying the Power App Solution

## Page info

| Page | Deployment Guide |
| :--- | :--- |
| Author | Rob Watts ([@robwatts365](https://github.com/robwatts365)) |
| **Version** | 1.0 |
| **Date** | 17/06/2024 |
