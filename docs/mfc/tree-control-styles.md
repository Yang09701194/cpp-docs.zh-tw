---
title: Tree Control Styles | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
dev_langs:
- C++
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
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
ms.openlocfilehash: 33908c85a1d2df039dbd0d120a98d89a23e0b060
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="tree-control-styles"></a>Tree Control Styles
Tree control ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) styles govern aspects of a tree control's appearance. You set the initial styles when you create the tree control. You can retrieve and change the styles after creating the tree control by using the [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) and [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) Windows functions, specifying **GWL_STYLE** for the `nIndex` parameter. For a complete list of styles, see [Tree View Control Window Styles](http://msdn.microsoft.com/library/windows/desktop/bb760013) in the Windows SDK.  
  
 The **TVS_HASLINES** style enhances the graphic representation of a tree control's hierarchy by drawing lines that link child items to their corresponding parent item. This style does not link items at the root of the hierarchy. To do so, you need to combine the **TVS_HASLINES** and **TVS_LINESATROOT** styles.  
  
 The user can expand or collapse a parent item's list of child items by double-clicking the parent item. A tree control that has the **TVS_SINGLEEXPAND** style causes the item being selected to expand and the item being unselected to collapse. If the mouse is used to single-click the selected item and that item is closed, it will be expanded. If the selected item is single-clicked when it is open, it will be collapsed.  
  
 A tree control that has the **TVS_HASBUTTONS** style adds a button to the left side of each parent item. The user can click the button to expand or collapse the child items as an alternative to double-clicking the parent item. **TVS_HASBUTTONS** does not add buttons to items at the root of the hierarchy. To do so, you must combine **TVS_HASLINES**, **TVS_LINESATROOT**, and **TVS_HASBUTTONS**.  
  
 The **TVS_EDITLABELS** style makes it possible for the user to edit the labels of tree control items. For more information about editing labels, see [Tree Control Label Editing](../mfc/tree-control-label-editing.md) later in this topic.  
  
 The **TVS_NOTOOLTIPS** style disables the automatic tool tip feature of tree view controls. This feature automatically displays a tool tip, containing the title of the item under the mouse cursor, if the entire title is not currently visible.  
  
## <a name="see-also"></a>See Also  
 [Using CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Controls](../mfc/controls-mfc.md)


