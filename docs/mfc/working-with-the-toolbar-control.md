---
title: Working with the Toolbar Control | Microsoft Docs
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
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
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
ms.openlocfilehash: 4a8bcb19890c1d00efcdfd9988515e724d9f8e39
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="working-with-the-toolbar-control"></a>Working with the Toolbar Control
This article explains how you can access the [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) object underlying a [CToolBar](../mfc/reference/ctoolbar-class.md) for greater control over your toolbars. This is an advanced topic.  
  
## <a name="procedures"></a>Procedures  
  
#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>To access the toolbar common control underlying your CToolBar object  
  
1.  Call [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).  
  
 `GetToolBarCtrl` returns a reference to a [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) object. You can use the reference to call member functions of the toolbar control class.  
  
> [!CAUTION]
>  While calling `CToolBarCtrl` **Get** functions is safe, use caution if you call the **Set** functions. This is an advanced topic. Normally you shouldn't need to access the underlying toolbar control.  
  
### <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Controls (Windows common controls)](../mfc/controls-mfc.md)  
  
-   [Toolbar fundamentals](../mfc/toolbar-fundamentals.md)  
  
-   [Docking and floating toolbars](../mfc/docking-and-floating-toolbars.md)  
  
-   [Dynamically resizing the toolbar](../mfc/docking-and-floating-toolbars.md)  
  
-   [Toolbar tool tips](../mfc/toolbar-tool-tips.md)  
  
-   [Flyby status bar updates](../mfc/toolbar-tool-tips.md)  
  
-   [Handling tool tip notifications](../mfc/handling-tool-tip-notifications.md)  
  
-   The [CToolBar](../mfc/reference/ctoolbar-class.md) and [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) classes  
  
-   [Handling customization notifications](../mfc/handling-customization-notifications.md)  
  
-   [Multiple toolbars](../mfc/toolbar-fundamentals.md)  
  
-   [Using your old toolbars](../mfc/using-your-old-toolbars.md)  
  
-   [Control bars](../mfc/control-bars.md)  
  
 For general information about using Windows common controls, see [Common Controls](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## <a name="see-also"></a>See Also  
 [MFC Toolbar Implementation](../mfc/mfc-toolbar-implementation.md)


