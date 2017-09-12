---
title: Application Settings, MFC DLL Wizard | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
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
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: a4721fbb1f0abfdda66dfb70ad1f4e44cf848fd3
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="application-settings-mfc-dll-wizard"></a>Application Settings, MFC DLL Wizard
Use this page of the MFC DLL wizard to design and add basic features to a new MFC DLL project.  
  
## <a name="dll-type"></a>DLL type  
 Select the type of DLL you want to create.  
  
 **Regular MFC DLL using shared MFC DLL**  
 Select this option to link the MFC library to your program as a shared DLL. Using this option, you cannot share MFC objects between your DLL and the calling application. Your program makes calls to the MFC library at run time. This option reduces the disk and memory requirements of your program if it is composed of multiple execution files that use the MFC library. Both Win32 and MFC programs can call functions in your DLL. You must redistribute the MFC DLL with this type of project.  
  
 **Regular MFC DLL with MFC statically linked**  
 Select this option to link your program statically to the MFC library at build time. Both Win32 and MFC programs can call functions in your DLL. While this option increases the size of your program, you do not need to redistribute the MFC DLL with this type of project. You cannot share MFC objects between your DLL and the calling application.  
  
 **MFC extension DLL**  
 Select this option if you want your program to make calls to the MFC library at run time, and if you want to share MFC objects between your DLL and the calling application. This option reduces the disk and memory requirements of your program, if it is composed of multiple executable files that all use the MFC library. Only MFC programs can call functions in your DLL. You must redistribute the MFC DLL with this type of project.  
  
## <a name="additional-features"></a>Additional features  
 Select whether your MFC DLL should support automation and whether it should support Windows sockets.  
  
 **Automation**  
 Select **Automation** to allow your program to manipulate objects implemented in another program. Selecting **Automation** also exposes your program to other Automation clients. See [Automation](../../mfc/automation.md) for more information.  
  
 **Windows sockets**  
 Select this option to indicate that your program supports Windows sockets. Windows sockets allow you to write programs that communicate over TCP/IP networks.  
  
 When your MFC DLL with Windows sockets support is created, [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) initializes support for sockets and the MFC header file StdAfx.h includes AfxSock.h.  
  
## <a name="see-also"></a>See Also  
 [MFC DLL Wizard](../../mfc/reference/mfc-dll-wizard.md)   
 [Creating an MFC DLL Project](../../mfc/reference/creating-an-mfc-dll-project.md)


