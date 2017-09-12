---
title: OnIdle Member Function | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
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
ms.openlocfilehash: ac9f493a6f3ffc734c9e214690734633184c9fd3
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="onidle-member-function"></a>OnIdle Member Function
When no Windows messages are being processed, the framework calls the [CWinApp](../mfc/reference/cwinapp-class.md) member function [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (described in the MFC Library Reference).  
  
 Override `OnIdle` to perform background tasks. The default version updates the state of user-interface objects such as toolbar buttons and performs cleanup of temporary objects created by the framework in the course of its operations. The following figure illustrates how the message loop calls `OnIdle` when there are no messages in the queue.  
  
 ![Message loop process](../mfc/media/vc387c1.gif "vc387c1")  
The Message Loop  
  
 For more information about what you can do in the idle loop, see [Idle Loop Processing](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>See Also  
 [CWinApp: The Application Class](../mfc/cwinapp-the-application-class.md)

