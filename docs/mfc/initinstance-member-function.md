---
title: InitInstance Member Function | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- InitInstance
dev_langs:
- C++
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
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
ms.openlocfilehash: 79983bf7027ee121f5843427262caac6174fde83
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="initinstance-member-function"></a>InitInstance Member Function
The Windows operating system allows you to run more than one copy, or "instance," of the same application. `WinMain` calls [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) every time a new instance of the application starts.  
  
 The standard `InitInstance` implementation created by the MFC Application Wizard performs the following tasks:  
  
-   As its central action, creates the document templates that in turn create documents, views, and frame windows. For a description of this process, see [Document Template Creation](../mfc/document-template-creation.md).  
  
-   Loads standard file options from an .ini file or the Windows registry, including the names of the most recently used files.  
  
-   Registers one or more document templates.  
  
-   For an MDI application, creates a main frame window.  
  
-   Processes the command line to open a document specified on the command line or to open a new, empty document.  
  
 You can add your own initialization code or modify the code written by the wizard.  
  
> [!NOTE]
>  MFC applications must be initialized as single threaded apartment (STA). If you call [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in your `InitInstance` override, specify `COINIT_APARTMENTTHREADED` (rather than `COINIT_MULTITHREADED`). For more information, see PRB: MFC Application Stops Responding When You Initialize the Application as a Multithreaded Apartment (828643) at [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
## <a name="see-also"></a>See Also  
 [CWinApp: The Application Class](../mfc/cwinapp-the-application-class.md)

