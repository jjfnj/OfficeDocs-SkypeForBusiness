---
title: "Skype for Business peer-to-peer activity report"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/24/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_ReportsS4BPeerActivity
- O365M_ReportsS4BPeerActivity
- O365P_ReportsS4BPeerActivity
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_UI_Elements
ms.custom: Adm_O365_FullSet
ms.assetid: d3b2d569-4ee9-44b8-92bf-d518142f0713

description: "Get a Skype for Business Peer-to-peer activity report, and learn how to interpret and customize it for your needs. "
---

# Skype for Business peer-to-peer activity report

The new Office 365 **Reports** dashboard shows you the activity overview across the Office 365 products in your organization. It enables you to drill in to individual product level reports to give you more granular insight about the activities within each product. For example, you can use the **Skype for Business peer-to-peer activity** report to see how much your users are using IM, audio, video, application sharing, and transferring files. Check out[Activity Reports in the Office 365 admin center](http://technet.microsoft.com/library/0d6dfb17-8582-4172-a9a9-aed798150263%28Office.14%29.aspx)
  
This report along with the other Skype for Business reports give you details on activity across your organization. These details are very helpful when you investigating, planning, and making other business decisions for your organization. 
  
> [!NOTE]
> You can see all of the Skype for Business reports when you log on as an administrator to the Office 365 admin center. 
  
## How to get to the Skype for Business peer-to-peer activity report

1. Go to the ** Office 365 admin center** > **Reports** > **Usage**.
    
2. On the **Usage** page, click **Skype for Business peer-to-peer activity** on the **Select a report list** on the left. Or, click the **Skype for Business activity** widget and then click **Skype for Business peer-to-peer activity** on the **Skype for Business activity** list.
    
     ![Skype peer to peer menu selected](../images/603ec74a-7f39-4e12-8f10-00979f7ee977.PNG)
  
    > [!IMPORTANT]
    > Depending on the Office 365 subscription you have, you might not see all the products and activity reports shown here. 
  
## Interpret the Skype for Business peer-to-peer activity report

You can get a view into your Skype for Business peer-to-peer activity by looking at **Activity**, **Users**, and **Minutes** charts.
  
![Skype peer to peer report with callouts.](../images/82dec398-ca05-46c7-b0fe-affcbfc0ddd5.PNG)
  
|||
|:-----|:-----|
|**1** <br/> |The **Skype for Business peer-to-peer activity** report can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days. <br/> |
|**2** <br/> |Each report has a date for when this report was generated. The reports usually reflect a 24- to 48-hour latency from time of activity.  <br/> |
|**3** <br/> |Use the interactive chart data on the **Activity** chart to understand usage trends and to see the total number of sessions per session type being held in your organization. It will show you the total number and types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** sessions across your organization. <br/> |
|**4** <br/> | Use the interactive chart data on the **Users** chart to understand usage trends and to see the number of unique users that are participating in peer-to-peer activities that are being held in your organization. It will show you the total number of users along with the types of **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** in peer-to-peer sessions. <br/> |
|**5** <br/> | Use the interactive chart data on the **Minutes** chart to understand usage trends and to see the number of minutes that are used by users doing peer-to-peer activities using audio and video. It will show you the total number of minutes of **Audio** and **Video** that is used in peer-to-peer sessions. <br/> |
|**6** <br/> | Each chart has an 'X' (horizontal) and 'Y' (vertical) axis. <br/>  On the **Activity** activity chart, the Y axis is the total number of IM, audio, video, application sharing and transferring files sessions that your users held in your organization. <br/>  On the **Users** activity chart, the Y axis is the total number users that held IM, audio, video, application sharing, and transferring files sessions. <br/>  On the **Minutes** activity chart, the Y axis is the total number of minutes that users across your organization spent using audio and video peer-to-peer sessions. <br/>  The X axis on both charts is the selected date range for this specific report. <br/> |
|**7** <br/> |You can filter the series you see on the chart by clicking on an item in the legend. For example, on the **Activity** chart, click or tap **IM**, **Audio**, **Video**, **Application sharing**, and **File transfers** to see only the info related to each one. Changing this selection doesn't change the info in the grid table. <br/> |
|**8** <br/> | The table shows you a breakdown of the peer-to-peer activities per user. This shows all users that have Skype for Business assigned to them and their peer-to-peer activities. You can add additional columns to the table. <br/> **User name** is the name of the user. <br/> **Deleted** indicates that the user's license was removed. <br/> > [!NOTE]>  Activity for a deleted user will still display in a report as long as he or she was licensed at some time during the selected time period. The **Deleted** column helps you to note that the user may no longer be active, but contributed to the data in the report.          **Deleted date** is the date on which the user's license was removed. <br/> **Last activity date (UTC)** is the last activity date (UTC) for that user. <br/> **IM** shows the total number of peer-to-peer sessions that the user used. <br/> **Audio** shows the total number of peer-to-peer sessions that used audio. <br/> **Video** shows the total number of peer-to-peer sessions that used video. <br/> **Application sharing** shows the total number of peer-to peer application sharing sessions. <br/> **File transfers** shows the total number of peer-to peer file transfer sessions. <br/> **Audio minutes** shows the total number of audio minutes that were used across your organization. <br/> **Video minutes** shows the total number of video minutes that were used across your organization. <br/>  If your organization's policies prevents you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **How do I hide user level details?** section in the[Activity Reports in the Office 365 admin center](http://technet.microsoft.com/library/0d6dfb17-8582-4172-a9a9-aed798150263%28Office.14%29.aspx).  <br/> |
|**9** <br/> |You can also export the report data into an Excel .csv file, by clicking or tapping **Export**.           <br/> ![Skype for Business Reporting Export Button.](../images/de7e2ab7-d70c-422f-a0ec-178b10f7dd51.png)This exports data of all users and enables you to do simple sorting and filtering for further analysis. If you have less than 2000 users, you can sort and filter within the table in the report itself. If you have more than 2000 users, in order to filter and sort, you will need to export the data.  <br/> |
|**10** <br/> |![Skype for Business Online Reporting Manage Button.](../images/4c8f5387-cebb-4d6c-b7d3-05c954a2c234.png)Click or tap the **Columns** icon in any of the columns to add or remove columns from the report.           <br/> |
   
## Want to see other Skype for Business reports?

- [Skype for Business activity report](skype-for-business-activity-report.md) You can see how much your users are using peer-to-peer, organized, and participated in conferencing sessions.
    
- [Skype for Business device usage report](skype-for-business-device-usage-report.md) You can to see the devices including Windows-based operating systems and mobile devices that have the Skype for Business app installed and are using it for IM and meetings.
    
- [Skype for Business conference organizer activity report](skype-for-business-conference-organizer-activity-report.md) You can see how much your users are organizing conferences that use IM, audio/video, application sharing, Web, dial-in/out - 3rd party, and dial-in/out - Microsoft.
    
- [Skype for Business conference participant activity report](skype-for-business-conference-participant-activity-report.md) You can see how many IM, audio/video, application sharing, Web and and dial-in/out conferencing conferences are being participated in.
    
- [Skype for Business users blocked report](skype-for-business-users-blocked-report.md) You can see the users in your organization that have been blocked from making PSTN calls.
    
- [Skype for Business PSTN usage report](skype-for-business-pstn-usage-report.md) You can see the number of minutes spent in inbound/outbound calls and cost for these calls.
    
- [Skype for Business users blocked report](skype-for-business-users-blocked-report.md) You can see details about the type of media being used, duration of the session, the client used and the conferencing URL.
    
## See also

#### Other Resources

[Activity Reports in the Office 365 admin center](http://technet.microsoft.com/library/0d6dfb17-8582-4172-a9a9-aed798150263%28Office.14%29.aspx)

