---
title: Registering Window Classes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WndProc
dev_langs:
- C++
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
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
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 9687fea9a7f9978b53ec2f7584225ddd534f06d3
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="registering-window-classes"></a>Registering Window Classes
Window "classes" in traditional programming for Windows define the characteristics of a "class" (not a C++ class) from which any number of windows can be created. This kind of class is a template or model for creating windows.  
  
## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Window Class Registration in Traditional Programs for Windows  
 In a traditional program for Windows, without MFC, you process all messages to a window in its "window procedure" or "**WndProc**." A **WndProc** is associated with a window by means of a "window class registration" process. The main window is registered in the `WinMain` function, but other classes of windows can be registered anywhere in the application. Registration depends on a structure that contains a pointer to the **WndProc** function together with specifications for the cursor, background brush, and so forth. The structure is passed as a parameter, along with the string name of the class, in a prior call to the **RegisterClass** function. Thus, a registration class can be shared by multiple windows.  
  
## <a name="window-class-registration-in-mfc-programs"></a>Window Class Registration in MFC Programs  
 In contrast, most window class registration activity is done automatically in an MFC framework program. If you are using MFC, you typically derive a C++ window class from an existing library class using the normal C++ syntax for class inheritance. The framework still uses traditional "registration classes," and it provides several standard ones, registered for you when needed. You can register additional registration classes by calling the [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) global function and then passing the registered class to the **Create** member function of `CWnd`. As described here, the traditional "registration class" in Windows is not to be confused with a C++ class.  
  
 For more information, see [Technical Note 1](../mfc/tn001-window-class-registration.md).  
  
## <a name="see-also"></a>See Also  
 [Creating Windows](../mfc/creating-windows.md)


