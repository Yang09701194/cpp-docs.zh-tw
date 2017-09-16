---
title: Changing List Control Styles | Microsoft Docs
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
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
caps.latest.revision: 12
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
ms.openlocfilehash: bfc54eaadf15d29aaa6317c7b286f10daa5b9453
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="changing-list-control-styles"></a>Changing List Control Styles
You can change the window style of a list control ([CListCtrl](../mfc/reference/clistctrl-class.md)) at any time after you create it. By changing the window style, you change the kind of view the control uses. For example, to emulate the Explorer, you might supply menu items or toolbar buttons for switching the control between different views: icon view, list view, and so on.  
  
 For example, when the user selects your menu item, you could make a call to [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) to retrieve the current style of the control and then call [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) to reset the style. For more information, see [Using List View Controls](http://msdn.microsoft.com/library/windows/desktop/bb774736) in the Windows SDK.  
  
 Available styles are listed in [Create](../mfc/reference/clistctrl-class.md#create). The styles `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, and `LVS_REPORT` designate the four list control views.  
  
## <a name="extended-styles"></a>Extended Styles  
 In addition to the standard styles for a list control, there is another set, referred to as extended styles. These styles, discussed in [Extended List View Styles](http://msdn.microsoft.com/library/windows/desktop/bb774732) in the Windows SDK, provide a variety of useful features that customize the behavior of your list control. To implement the behavior of a certain style (such as hover selection), make a call to [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), passing the needed style. The following example demonstrates the function call:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  For hover selection to work, you must also have either **LVS_EX_ONECLICKACTIVATE** or **LVS_EX_TWOCLICKACTIVATE** turned on.  
  
## <a name="see-also"></a>See Also  
 [Using CListCtrl](../mfc/using-clistctrl.md)   
 [Controls](../mfc/controls-mfc.md)


