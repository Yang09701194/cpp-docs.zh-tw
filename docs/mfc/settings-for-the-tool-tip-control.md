---
title: Settings for the Tool Tip Control | Microsoft Docs
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
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
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
ms.openlocfilehash: 1fe26a166503e772c0ed7241cbbdb937c65b4211
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="settings-for-the-tool-tip-control"></a>Settings for the Tool Tip Control
You can set the tool tip control ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) to be either active or inactive. When you set it to be active, the tool tip control appears when the cursor is on a tool. When you set it to be inactive, the tool tip control does not appear, even if the cursor is on a tool. Call [Activate](../mfc/reference/ctooltipctrl-class.md#activate) to activate or deactivate a tool tip control.  
  
 You can set an active tool tip to display the tool tip when the cursor is on a tool, whether or not the tool tip control's owner window is active or inactive, by using the **TTS_ALWAYSTIP** style. If you do not use this style, the tool tip control appears when the tool's owner window is active, but not when it is inactive.  
  
 Most applications contain toolbars with tools that correspond to menu commands. For such tools, it is convenient for the tool tip control to display the same text as the corresponding menu item. The system automatically strips the ampersand (&) accelerator characters from all strings passed to a tool tip control, unless the control has the **TTS_NOPREFIX** style.  
  
## <a name="see-also"></a>See Also  
 [Using CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Controls](../mfc/controls-mfc.md)


