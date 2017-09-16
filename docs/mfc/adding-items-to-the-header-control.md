---
title: Adding Items to the Header Control | Microsoft Docs
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
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
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
ms.translationtype: HT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 2462eb917e8466f5fd826854e781bedb1c39b848
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="adding-items-to-the-header-control"></a>Adding Items to the Header Control
After creating your header control ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) in its parent window, add as many "header items" as you need: usually one per column.  
  
### <a name="to-add-a-header-item"></a>To add a header item  
  
1.  Prepare an [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) structure.  
  
2.  Call [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), passing the structure.  
  
3.  Repeat steps 1 and 2 for additional items.  
  
 For more information, see [Adding an Item to a Header Control](http://msdn.microsoft.com/library/windows/desktop/bb775238) in the Windows SDK.  
  
## <a name="see-also"></a>See Also  
 [Using CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Controls](../mfc/controls-mfc.md)


