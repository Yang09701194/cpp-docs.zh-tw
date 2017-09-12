---
title: Communicating with a Tree Control | Microsoft Docs
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
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
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
ms.openlocfilehash: 8ab92bdc6b811f2590a66281e33c5e269df0f369
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="communicating-with-a-tree-control"></a>Communicating with a Tree Control
You use different methods for calling member functions in a [CTreeCtrl](../mfc/reference/ctreectrl-class.md) object depending on how the object was created:  
  
-   If the tree control is in a dialog box, use a member variable of type `CTreeCtrl` that you create in the dialog box class.  
  
-   If the tree control is a child window, use the `CTreeCtrl` object (or pointer) you used to construct the object.  
  
-   If you're using a `CTreeView` object, use the function [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) to get a reference to the tree control. You can initialize another reference with this value or assign the address of the reference to a `CTreeCtrl` pointer.  
  
## <a name="see-also"></a>See Also  
 [Using CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Controls](../mfc/controls-mfc.md)


