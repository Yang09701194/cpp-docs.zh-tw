---
title: Providing Drag-and-Drop Support for Header Items | Microsoft Docs
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
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
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
ms.openlocfilehash: c8f65b9cbc240523ba7dd8e615a83e16a0ccab83
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Providing Drag-and-Drop Support for Header Items
To provide drag-and-drop support for header items, specify the `HDS_DRAGDROP` style. Drag-and-drop support for header items gives the user the ability to reorder the header items of a header control. The default behavior provides a semitransparent drag image of the header item being dragged and a visual indicator of the new position, if the header item is dropped.  
  
 As with common drag-and-drop functionality, you can extend the default drag-and-drop behavior by handling the **HDN_BEGINDRAG** and **HDN_ENDDRAG** notifications. You can also customize the appearance of the drag image by overriding the [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) member function.  
  
> [!NOTE]
>  If you are providing drag-and-drop support for an embedded header control in a list control, see the Extended Style section in the [Changing List Control Styles](../mfc/changing-list-control-styles.md) topic.  
  
## <a name="see-also"></a>See Also  
 [Using CHeaderCtrl](../mfc/using-cheaderctrl.md)


