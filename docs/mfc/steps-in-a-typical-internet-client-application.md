---
title: Steps in a Typical Internet Client Application | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 3380cae7676f307c90c49e0f778b096d89aa7a3f
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="steps-in-a-typical-internet-client-application"></a>Steps in a Typical Internet Client Application
The following table shows the steps you might perform in a typical Internet client application.  
  
|Your goal|Actions you take|Effects|  
|---------------|----------------------|-------------|  
|Begin an Internet session.|Create a [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Initializes WinInet and connects to server.|  
|Set an Internet query option (time-out limit or number of retries, for example).|Use [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|Returns FALSE if operation was unsuccessful.|  
|Establish a callback function to monitor the status of the session.|Use [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback).|Establishes a callback to [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback). Override `OnStatusCallback` to create your own callback routine.|  
|Connect to an Internet server, intranet server, or local file.|Use [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl).|Parses the URL and opens a connection to the specified server. Returns a [CStdioFile](../mfc/reference/cstdiofile-class.md) (if you pass `OpenURL` a local file name). This is the object through which you access data retrieved from the server or file.|  
|Read from the file.|Use [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|Reads the specified number of bytes using a buffer you supply.|  
|Handle exceptions.|Use the [CInternetException](../mfc/reference/cinternetexception-class.md) class.|Handles all common Internet exception types.|  
|End the Internet session.|Dispose of the [CInternetSession](../mfc/reference/cinternetsession-class.md) object.|Automatically cleans up open file handles and connections.|  
  
## <a name="see-also"></a>See Also  
 [Win32 Internet Extensions (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Prerequisites for Internet Client Classes](../mfc/prerequisites-for-internet-client-classes.md)   
 [Writing an Internet Client Application Using MFC WinInet Classes](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

