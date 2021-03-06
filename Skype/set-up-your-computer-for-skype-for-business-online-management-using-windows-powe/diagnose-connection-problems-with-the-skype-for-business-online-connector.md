---
title: "Diagnose connection problems with the Skype for Business Online Connector"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# Diagnose connection problems with the Skype for Business Online Connector

This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online. See the following sections:
  
- [Import-Module error caused by Windows PowerShell execution policy](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_PowerShellExecutionPolicy)
    
- [Import-Module Error caused by incorrect version of Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_IncorrectVersion)
    
- [Failed to connect to Live ID Server](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedConnect)
    
- [Failed to load Live ID module](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedLoad)
    
- [Logon failed for the user](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_LogonFailed)
    
- [The user does not have permission to manage this tenant](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_UserPermission)
    
- [Ability to connect to tenant has been disabled in Skype for Business Online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_AbilityConnect)
    
- [The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## Import-Module error caused by Windows PowerShell execution policy
<a name="BKMK_PowerShellExecutionPolicy"> </a>

The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console. At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned. If it has not, then you will receive the following error message when you attempt to import the module:
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

To resolve this issue, start PowerShell as an administrator, and then run the following command:
  
```
Set-ExecutionPolicy RemoteSigned
```

For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## Import-Module Error caused by incorrect version of Windows PowerShell
<a name="BKMK_IncorrectVersion"> </a>

The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0. If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [http://www.microsoft.com/en-us/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939).
  
## Failed to connect to Live ID Server
<a name="BKMK_FailedConnect"> </a>

There are typically three reasons why your connection attempt might fail with the following error message:
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

Often this error means that the Microsoft Online Services Sign-in Assistant is not running. You can verify the status of this service by running the following command from the PowerShell prompt:
  
```
Get-Service "msoidsvc"
```

If the service is not running, start the service by using this command:
  
```
Start-Service "msoidsvc"
```

If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server. To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Try logging on to Office 365 from there. If this fails, you are probably experiencing network connection issues.
  
Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value. If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue. In this case, contact Office 365 Support.
  
## Failed to load Live ID module
<a name="BKMK_FailedLoad"> </a>

One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant. If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177).
  
## Logon failed for the user
<a name="BKMK_LogonFailed"> </a>

When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account. If you do not, logon will fail along with an error message similar to this:
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

If you think that you are using a valid user account and that you have the correct password, try logging on again. If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/). If you are unable to log on there, contact Office 365 Support.
  
## The user does not have permission to manage this tenant
<a name="BKMK_UserPermission"> </a>

You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group. If you are not, your connection attempt will fail, and you'll receive the following error message:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.
  
## Ability to connect to tenant has been disabled in Skype for Business Online
<a name="BKMK_AbilityConnect"> </a>

To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`. If it is not, your connection will fail, and you'll receive the following error message:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.
  
## The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded
<a name="BKMK_MaxNumberShellsUser"> </a>

Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online. If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

The only way to resolve this issue is to close one or more of the previous connections. When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session. This will help you to prevent this issue.
  
## The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded
<a name="BKMK_MaxNumberShellsTenant"> </a>

Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than nine simultaneous connections. For example, three administrators might each have three open sessions. If a fourth administrator tries to make a connection (resulting in a total of 10 simultaneous connections), this attempt will fail, with the following error message:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

The only way to resolve this issue is to close one or more of the previous connections. When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session. This will help you to prevent this issue.
  

