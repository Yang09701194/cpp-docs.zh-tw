---
title: Handling Reflected Messages | Microsoft Docs
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
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
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
ms.openlocfilehash: 1366210ad53c7b04e36dfcf3afef7063d61c4b01
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="handling-reflected-messages"></a>Handling Reflected Messages
Message reflection lets you handle messages for a control, such as `WM_CTLCOLOR`, **WM_COMMAND**, and **WM_NOTIFY**, within the control itself. This makes the control more self-contained and portable. The mechanism works with Windows common controls as well as with ActiveX controls (formerly called OLE controls).  
  
 Message reflection lets you reuse your `CWnd`-derived classes more readily. Message reflection works via [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), using special **ON_XXX_REFLECT** message map entries: for example, **ON_CTLCOLOR_REFLECT** and **ON_CONTROL_REFLECT**. [Technical Note 62](../mfc/tn062-message-reflection-for-windows-controls.md) explains message reflection in more detail.  
  
## <a name="what-do-you-want-to-do"></a>What do you want to do  
  
-   [Learn more about message reflection](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implement message reflection for a common control](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [Implement message reflection for an ActiveX control](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>See Also  
 [Declaring Message Handler Functions](../mfc/declaring-message-handler-functions.md)

