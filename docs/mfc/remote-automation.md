---
title: Remote Automation | Microsoft Docs
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
- MFC COM, Remote Automation
- Automation objects [MFC]
- DCOM [MFC], Remote Automation
- Automation objects [MFC], creating
- Remote Automation [MFC]
- MFC, COM support
- Automation controller [MFC]
- COM, Remote Automation [MFC]
ms.assetid: 363f87fb-08fa-4458-b089-b46365a6d4f2
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
ms.openlocfilehash: 44f579ff2b10d4e8e4e655110a4ec9835b192fd8
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="remote-automation"></a>Remote Automation
> [!NOTE]
>  It is recommended that Visual C++ .NET developers use DCOM rather than Remote Automation for new applications. Visual C++ .NET does not support Windows 95. Cases in which you would need to support Remote Automation are described in [Where Does Remote Automation Fit In](where-does-remote-automation-fit-in-q.md).  
  
 Remote Automation is a type of [Automation](../mfc/automation.md) that allows an interface consumer to execute an interface provider that resides on another machine, for example, on a network.  
  
 This article explains how to create Automation objects that can be invoked and executed remotely, and how to create Automation controllers that can use these Remote Automation objects. It also examines configuration options and points out the major differences between Remote Automation and DCOM (the distributed version of COM and OLE that allows interfaces other than those related to automation to be invoked and executed remotely).  
  
## <a name="in-this-section"></a>In This Section  
 [History of DCOM (Distributed Component Object Model)](../mfc/history-of-dcom.md)  
  
 [Where Does Remote Automation Fit In](where-does-remote-automation-fit-in-q.md)  
  
 [What Does Remote Automation Provide](what-does-remote-automation-provide-q.md)  
  
 [Remote Automation Security](../mfc/security-in-remote-automation.md)  
  
 [Threading Models](../mfc/remote-automation-threading-models.md)  
  
 [Installation](../mfc/remote-automation-installation.md)  
  
 [The Automation Manager](../mfc/automation-manager-mfc.md)  
  
-   [The Remote Automation Connection Manager](../mfc/remote-automation-connection-manager.md)  
  
-   [Remote Automation User Components](../mfc/remote-automation-user-components.md)  
  
 [Creating Programs That Use Remote Automation](../mfc/creating-programs-that-use-remote-automation.md)  
  
 [Running Remote Automation Using AUTOCLIK and AUTODRIV](../mfc/running-remote-automation-using-autoclik-and-autodriv.md)  
  
## <a name="see-also"></a>See Also  
 [MFC COM](../mfc/mfc-com.md)   
 [Automation](../mfc/automation.md)

