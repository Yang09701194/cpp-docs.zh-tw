---
title: Message Handlers | Microsoft Docs
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
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
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
ms.openlocfilehash: 4c645aba2c37f403121b311f12863334277e5612
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="message-handlers"></a>Message Handlers
In MFC, a dedicated *handler* function processes each separate message. Message-handler functions are member functions of a class. This documentation uses the terms *message-handler member function*, *message-handler function*, *message handler*, and *handler* interchangeably. Some kinds of message handlers are also called "command handlers."  
  
 Writing message handlers accounts for a large proportion of your work in writing a framework application. This article family describes how the message-processing mechanism works.  
  
 What does the handler for a message do It does whatever you want done in response to that message. You can create the handlers by using the Properties window of the class, and then fill in the handler's code using the source code editor.  
  
 You can use all of the facilities of Microsoft Visual C++ and MFC to write your handlers. For a list of all classes, see [Class Library Overview](../mfc/class-library-overview.md) in the *MFC Reference*.  
  
## <a name="see-also"></a>See Also  
 [Messages and Commands in the Framework](../mfc/messages-and-commands-in-the-framework.md)


