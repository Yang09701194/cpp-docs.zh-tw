---
title: Adding Tabs to a Tab Control | Microsoft Docs
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
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
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
ms.openlocfilehash: 9da423b56c254bc58bcbe940ebcd366e83c8f385
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="adding-tabs-to-a-tab-control"></a>Adding Tabs to a Tab Control
After creating the tab control ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), add as many tabs as you need.  
  
### <a name="to-add-a-tab-item"></a>To add a tab item  
  
1.  Prepare a [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure.  
  
2.  Call [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), passing the structure.  
  
3.  Repeat steps 1 and 2 for additional tab items.  
  
 For more information, see [Creating a Tab Control](http://msdn.microsoft.com/library/windows/desktop/bb760550) in the Windows SDK.  
  
## <a name="see-also"></a>See Also  
 [Using CTabCtrl](../mfc/using-ctabctrl.md)   
 [Controls](../mfc/controls-mfc.md)


