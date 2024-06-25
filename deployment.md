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
*	Teams Telephony Administrator, Teams Communication Administrator or Teams Administrator role.
* Emergency Calling Policy
* Network topology configured in Microsoft Teams
  


### Emergency Locations:

When creating Emergency Locations for this solution, it is important to add Places, instead of using the Civic Address, as you are able to change the names of these after initial creation. Once a Civic address is created, it is validated and can not be modified, only deleted. 

It is also important to link your subnets, Wi-Fi access points, Switches and ports to the Places that you create. 

There is benefits in doing it this way, as you'll be able to define different zones of a building (Civic Address) to make more specific locations, if your IP subnets are configured this way.  

<img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/c7c70e6d-1c34-4c2c-97dc-517ac943f242" width="200" />  


<img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/8403ca12-4caa-4c01-906a-6229209a1c77" width="200" />  

> [!NOTE]
  >  You should use a naming convention with a static prefix to ensure all locations are captured, with a single string denoting the different locations, like a site reference.
  [PREFIX] [LOCATION IDENTIFIER] 
  *(e.g. **Loc** SOUTHAMPTON)* 

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

1) Download the Solution export.
      | Version | Notes |
   | :--- | :--- |
   | [Managed Solution](ExtendEmergencyCallingNotifications_managed.zip) | If you're only looking to use the Core Solution. |
   | [Unmanaged Solution](ExtendEmergencyCallingNotifications_unmanaged.zip) | If you're looking to tweek/extend the solution further. |  
2) Nagivate to [Power Apps](https://make.powerapps.com/). Remember to sign in with the **Service Account** you created above. 
3) From the left rail, select **Solutions**  
   <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/ad4c6f0d-34d0-435a-8a76-12c6ce6da6c8" width="200" />
5) Select "Import Solution"  
   <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/75d374b7-a23a-4e32-bdbe-670b94ecd626" width="200" />
7) Click "Browse"  
   <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/f63bb62e-08ae-4868-8417-11309ebadd12" width="200" />
9) Select the downloaded solution. 
10) Click "Next"
11) Click "Next" again. 
12) Verify and sign in to the connectors.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/d3e8944d-9644-401c-9423-a2a581b11666" width="200" />
14) Click "Next"
15) For **'SPOSite'**, select the SharePoint site where your list resides. 
16) For **'SPOList'**, select your list 
17) For **Site Prefix**, enter the Prefix as detailed in the pre-requisites.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/3122a46c-ba75-499e-9144-cddbd596cc5c" width="200" />
19) Click "Import".

### Configure Teams Emergency Calling policies

Now that you've imported the solution, you need to set your Teams Emergency calling policy to send the notification to the **Service Account**, linked above. 

To do this:
1) Log in to the Teams Admin Center. 
2) Navigate to **Voice > Emergency policies** on the left rail.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/b5b69baf-73d2-4a6b-8ad5-e647d271f4b3" width="200" />
3) Select the Global policy.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/630d0ad5-8c48-406d-ba85-27480575af2e" width="200" />
4) Under Emergency numbers, click "Add"  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/f86acfaf-fbc1-4bbc-ae31-adef2aa82c5f" width="200" />
5) Change Notification mode to "Send notification only".
6) Search for your Service Account, click add.  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/a5db9c3c-fd7c-4273-b10d-d2e66d103b29" width="200" />
7) Click "Apply".  
    <img src="https://github.com/robwatts365/MicrosoftTeamsPhone-ExtendEmergencyCalling/assets/65971102/948692b6-8020-4491-bb13-25c66cbffb00" width="200" />
 

## Page info

| Page | Deployment Guide |
| :--- | :--- |
| Author | Rob Watts ([@robwatts365](https://github.com/robwatts365)) |
| **Version** | 1.0 |
| **Date** | 17/06/2024 |
