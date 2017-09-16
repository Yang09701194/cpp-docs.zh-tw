---
title: Tree Control Notification Messages | Microsoft Docs
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
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
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
ms.openlocfilehash: fa73f84bbbd6e8d4318b038831ccdd5b1721e9c6
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="tree-control-notification-messages"></a>Tree Control Notification Messages
A tree control ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sends the following notification messages as **WM_NOTIFY** messages:  
  
|Notification message|Description|  
|--------------------------|-----------------|  
|**TVN_BEGINDRAG**|Signals the start of a drag-and-drop operation|  
|**TVN_BEGINLABELEDIT**|Signals the start of in-place label editing|  
|**TVN_BEGINRDRAG**|Signals the start of a drag-and-drop operation, using the right mouse button|  
|**TVN_DELETEITEM**|Signals the deletion of a specific item|  
|**TVN_ENDLABELEDIT**|Signals the end of label editing|  
|**TVN_GETDISPINFO**|Requests information that the tree control requires to display an item|  
|**TVN_ITEMEXPANDED**|Signals that a parent item's list of child items was expanded or collapsed|  
|**TVN_ITEMEXPANDING**|Signals that a parent item's list of child items is about to be expanded or collapsed|  
|**TVN_KEYDOWN**|Signals a keyboard event|  
|**TVN_SELCHANGED**|Signals that the selection has changed from one item to another|  
|**TVN_SELCHANGING**|Signals that the selection is about to be changed from one item to another|  
|**TVN_SETDISPINFO**|Notification to update the information maintained for an item|  
  
## <a name="see-also"></a>See Also  
 [Using CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Controls](../mfc/controls-mfc.md)


