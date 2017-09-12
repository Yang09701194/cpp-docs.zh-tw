---
title: ToolBar Control Styles | Microsoft Docs
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
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
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
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 383120b1eecd7db663ef878c386f51ad6a2a92f8
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="toolbar-control-styles"></a>ToolBar Control Styles
[CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md) has a set of style flags that determine the appearance and behavior of the button. You can set a combination of these flags by calling             [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). This topic lists the style flag values and their meanings.  
  
## <a name="property-values"></a>Property Values  
 The following values determine the type of button that the control represents:  
  
 TBBS_BUTTON  
 Standard pushbutton (default).  
  
 TBBS_CHECKBOX  
 Check box.  
  
 TBBS_CHECKGROUP  
 The start of a group of checkboxes.  
  
 TBBS_GROUP  
 The start of a group of buttons.  
  
 TBBS_SEPARATOR  
 Separator.  
  
 The following values represent the current status of the control:  
  
 TBBS_CHECKED  
 Check box is checked.  
  
 TBBS_DISABLED  
 Control is disabled.  
  
 TBBS_INDETERMINATE  
 Check box is in an indeterminate state.  
  
 TBBS_PRESSED  
 Button is pressed.  
  
 The following value changes the layout of the button in the toolbar:  
  
 TBBS_BREAK  
 Places the item on a new line or in a new column without separating columns.  
  
## <a name="remarks"></a>Remarks  
 The current style is stored in                 [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Do not set a new value in                 `m_nStyle` directly, because some derived classes perform additional processing when you call                 `SetStyles`.  
  
 The visual manager determines the appearance of buttons in each state. See                 [Visualization Manager](../../mfc/visualization-manager.md) for more information.  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>See Also  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Visualization Manager](../../mfc/visualization-manager.md)



