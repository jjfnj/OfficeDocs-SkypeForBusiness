---
title: "Set auto attendant languages for Audio Conferencing"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
description: "See how to select the auto-attendant lanugages for a dial-in conferencing number."
---

# Set auto attendant languages for Audio Conferencing

The Audio Conferencing auto attendant for Skype for Business and Microsoft Teams can greet audio callers in a number of different languages when they join a meeting.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  You can configure the languages on domestic audio access phone numbers only.
  
## Set the conferencing auto attendant languages

You must be an [About Office 365 admin roles](http://technet.microsoft.com/library/da585eea-f576-4f55-a1e0-87090b6aaa9d%28Office.14%29.aspx) or[About Office 365 admin roles](http://technet.microsoft.com/library/da585eea-f576-4f55-a1e0-87090b6aaa9d%28Office.14%29.aspx) to perform this step.
  
1. Sign in to Office 365 with your work or school account.
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.
    
4. Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**. 
    
5. On the **Set languages** page, click the **Primary language** list to view the complete list of available languages. If you need to, click each of the **Secondary languages** lists to select secondary language.
    
    > [!NOTE]
    > The primary and secondary languages that are supported are listed. The order in which you select them in the lists will be the order of the languages presented to callers. 
  
6. Click **Save**.
    
## Want else should I know?

- To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](audio-conferencing-supported-languages.md).
    
- Languages can be set for dedicated but not for shared phone numbers.
    
- To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).
    
## Want to use Windows PowerShell?

To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) and[Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.
  
To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## See also

#### Other Resources

[Set up Audio Conferencing for Skype for Business and Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

