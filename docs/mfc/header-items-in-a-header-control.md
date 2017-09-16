---
title: Header Items in a Header Control | Microsoft Docs
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
- header controls [MFC], header items in
- header items in header controls [MFC]
- CHeaderCtrl class [MFC], header items in
- controls [MFC], header
ms.assetid: ac79ef1f-a671-4ab2-93e9-b1aa016a48bf
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
ms.openlocfilehash: 65f579669d62b50686925587001362a3251ca0e4
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="header-items-in-a-header-control"></a>Header Items in a Header Control
You have considerable control over the appearance and behavior of the header items that make up a header control ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)). Each header item can have a string, a bitmapped image, an image from an associated image list, or an application-defined 32-bit value associated with it. The string, bitmap, or image is displayed in the header item.  
  
 You can customize the appearance and contents of new items when they are created by making a call [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem) or by modifying an existing item, with a call to [CHeaderCtrl::GetItem](../mfc/reference/cheaderctrl-class.md#getitem) and [CHeaderCtrl::SetItem](../mfc/reference/cheaderctrl-class.md#setitem).  
  
## <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Customizing the header item's appearance](../mfc/customizing-the-header-item-s-appearance.md)  
  
-   [Ordering items in the header control](../mfc/ordering-items-in-the-header-control.md)  
  
-   [Providing drag-and-drop support for the header items](../mfc/providing-drag-and-drop-support-for-header-items.md)  
  
-   [Using image lists with header controls](../mfc/using-image-lists-with-header-controls.md)  
  
## <a name="see-also"></a>See Also  
 [Using CHeaderCtrl](../mfc/using-cheaderctrl.md)


