---
title: Settings for the Toolbar Control | Microsoft Docs
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
- toolbar controls [MFC], about toolbar controls
- CToolBarCtrl class [MFC], settings
ms.assetid: 025ba920-b3ee-4d82-9367-e652cd7875b9
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
ms.openlocfilehash: 6f4f5851db38fdef582d5aaec6961bee53f8c0f0
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="settings-for-the-toolbar-control"></a>Settings for the Toolbar Control
The buttons on a toolbar can display a bitmap, a string, or both. By default, the image size is set to the dimensions of 16 by 15 pixels. All buttons are the same width, by default 24 by 22 pixels. A toolbar's height is determined by the height of the buttons, and a toolbar's width is the same as the width of the parent window's client area, also by default.  
  
 A toolbar can have built-in customization features, including a system-defined customization dialog box, that allow the user to insert, delete, or rearrange toolbar buttons. An application determines whether the customization features are available to the user and controls the extent to which the user can customize the toolbar. For more information about customizing the toolbar, see class [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) in the *MFC Reference*.  
  
## <a name="see-also"></a>See Also  
 [Using CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Controls](../mfc/controls-mfc.md)


