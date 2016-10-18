---
title: Tftp
description: "Windows Commands"
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 772f19a8-dafe-45cd-878a-f5691f6568ef vhorne
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
---

# Tftp

>Applies To: Windows Server&reg; 2016, Windows Server&reg; 2012 R2, Windows Server&reg; 2012

Transfers files to and from a remote computer, typically a computer running UNIX, that is running the Trivial File Transfer Protocol (TFTP) service or daemon. TFTP is typically used by embedded devices or systems that retrieve firmware, configuration information, or a system image during the boot process from a TFTP server.   
## Syntax  
```  
tftp [-i] [<Host>] [{get | put}] <Source> [<Destination>]  
```  
### Parameters  
|Parameter|Description|  
|-------------|---------------|  
|-i|Specifies binary image transfer mode (also called octet mode). In binary image mode, the file is transferred in one-byte units. Use this mode when transferring binary files. If **-i** is omitted, the file is transferred in ASCII mode. This is the default transfer mode. This mode converts the end-of-line (EOL) characters to an appropriate format for the specified computer. Use this mode when transferring text files. If a file transfer is successful, the data transfer rate is displayed.|  
|<Host>|Specifies the local or remote computer.|  
|put|Transfers the file *Source* on the local computer to the file *Destination* on the remote computer. Because the TFTP protocol does not support user authentication, the user must be logged onto the remote computer, and the files must be writable on the remote computer.|  
|get|Transfers the file *Destination* on the remote computer to the file *Source* on the local computer.|  
|<Source>|Specifies the file to transfer.|  
|<Destination>|Specifies where to transfer the file.|  
## Remarks  
-   You can install the TFTP client using the Add Features Wizard.  
-   The TFTP protocol does not support any authentication or encryption mechanism, and as such can introduce a security risk when present. Installing the TFTP client is not recommended for systems connected to the Internet.  
-   The TFTP client is optional software, and marked as deprecated on Windows Vista and later versions of the Windows operating system. A TFTP server service is no longer provided by Microsoft for security reasons.  
## <a name="BKMK_Examples"></a>Examples  
Copy the file **boot.img** from the remote computer **Host1**.  
```  
tftp ???i Host1 get boot.img  
```  
## Additional references  
-   [Command-Line Syntax Key](Command-Line-Syntax-Key.md)  