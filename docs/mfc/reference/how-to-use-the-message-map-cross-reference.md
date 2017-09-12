---
title: 'How to: Use the Message-Map Cross-Reference | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: 11
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
ms.openlocfilehash: b25095aab5f565df033945a9523d21fd14ae567c
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="how-to-use-the-message-map-cross-reference"></a>How to: Use the Message-Map Cross-Reference
In entries labeled \<memberFxn>, write your own member function for a derived [CWnd](../../mfc/reference/cwnd-class.md) class. Give your function any name you like. Other functions, such as `OnActivate`, are member functions of class `CWnd`. If called, they pass the message to the `DefWindowProc` Windows function. To process Windows notification messages, override the corresponding `CWnd` function in your derived class. Your function should call the overridden function in your base class to let the base class and Windows respond to the message.  
  
 In all cases, put the function prototype in the `CWnd`-derived class header, and code the message map entry as shown.  
  
 The following terms are used:  
  
|Term|Definition|  
|----------|----------------|  
|id|Any user-defined menu item ID (**WM_COMMAND** messages) or control ID (child window notification messages).|  
|"message" and "wNotifyCode"|Windows message IDs as defined in WINDOWS.H.|  
|nMessageVariable|Name of a variable that contains the return value from the **RegisterWindowMessage** Windows function.|  
  
## <a name="see-also"></a>See Also  
 [Message Maps](../../mfc/reference/message-maps-mfc.md)


