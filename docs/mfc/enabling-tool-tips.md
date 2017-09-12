---
title: Enabling Tool Tips | Microsoft Docs
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
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
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
ms.openlocfilehash: ee1005229690073748667706bc3ce6b8609b0ea8
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="enabling-tool-tips"></a>Enabling Tool Tips
You can enable tool tip support for the child controls of a window (such as the controls on a form view or dialog box).  
  
### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>To enable tool tips for the child controls of a window  
  
1.  Call `EnableToolTips` for the window for which you want to provide tool tips.  
  
2.  Provide a string for each control in your [TTN_NEEDTEXT notification](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) handler. The handler is in the message map of the window that contains the child controls (for example, your form view class). This handler should call a function that identifies the control and sets **pszText** to specify the text used by the tool tip control.  
  
## <a name="see-also"></a>See Also  
 [Tool Tips in Windows Not Derived from CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)


