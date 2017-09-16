---
title: How Noncommand Messages Reach Their Handlers | Microsoft Docs
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
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
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
ms.openlocfilehash: 512c69c81e2d2226fd3336a911e62c21e4ad67ad
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="how-noncommand-messages-reach-their-handlers"></a>How Noncommand Messages Reach Their Handlers
Unlike commands, standard Windows messages do not get routed through a chain of command targets but are usually handled by the window to which Windows sends the message. The window might be a main frame window, an MDI child window, a standard control, a dialog box, a view, or some other kind of child window.  
  
 At run time, each Windows window is attached to a window object (derived directly or indirectly from `CWnd`) that has its own associated message map and handler functions. The framework uses the message map — as for a command — to map incoming messages to handlers.  
  
## <a name="see-also"></a>See Also  
 [How the Framework Calls a Handler](../mfc/how-the-framework-calls-a-handler.md)


