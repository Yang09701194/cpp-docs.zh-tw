---
title: Setting the Mode of a CStatusBarCtrl Object | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
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
ms.openlocfilehash: de773e6298a5bb33de9b3b07faa33f57fdbd7132
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Setting the Mode of a CStatusBarCtrl Object
There are two modes for a `CStatusBarCtrl` object: simple and nonsimple. In the majority of cases, your status bar control will have one or more parts, along with text and perhaps an icon or icons. This is called the nonsimple mode. For more information on this mode, see [Initializing the Parts of a CStatusBarCtrl Object](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 However, there are cases where you only need to display a single line of text. In this case, the simple mode is sufficient for your needs. To change the mode of the `CStatusBarCtrl` object to simple, make a call to the [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) member function. Once the status bar control is in simple mode, set the text by calling the **SetText** member function, passing 255 as the value for the **nPane** parameter.  
  
 You can use the [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) function to determine what mode the `CStatusBarCtrl` object is in.  
  
> [!NOTE]
>  If the status bar object is being changed from nonsimple to simple, or vice versa, the window is immediately redrawn and, if applicable, any defined parts are automatically restored.  
  
## <a name="see-also"></a>See Also  
 [Using CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Controls](../mfc/controls-mfc.md)


