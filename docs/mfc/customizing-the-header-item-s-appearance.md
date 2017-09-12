---
title: Customizing the Header Item&#39;s Appearance | Microsoft Docs
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
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
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
ms.openlocfilehash: 27f5bc3f96a06c21b559462ea5d003b9d7872a69
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="customizing-the-header-item39s-appearance"></a>Customizing the Header Item&#39;s Appearance
By setting the *dwStyle* parameter when you first create a header control ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), you can define the appearance and behavior of header items or of the header control itself.  
  
 Here is a sampling of the styles you can set, and their purpose:  
  
-   To make a header item look like a pushbutton, use the `HDS_BUTTONS` style.  
  
     Use this style if you want to carry out actions in response to mouse clicks on a header item, such as sorting data by a particular column, as is done in Microsoft Outlook.  
  
-   To give the header items a "hot tracking" appearance when the mouse cursor passes over them, use the `HDS_HOTTRACK` style.  
  
     Hot tracking displays a 3D outline as the pointer passes over an item in an otherwise flat bar.  
  
-   To indicate that the header control should be hidden, use the `HDS_HIDDEN` style.  
  
     The `HDS_HIDDEN` style indicates that the header control is intended to be used as a data container and not a visual control. This style does not automatically hide the control but, instead, affects the behavior of `CHeaderCtrl::Layout`. The value returned in the **cy** member of the `WINDOWPOS` structure will be zero indicating that the control should not be visible to the user.  
  
 For more information about these properties, see [Items](http://msdn.microsoft.com/library/windows/desktop/bb775238) in the Windows SDK. For information about adding items to a header control, see [Adding Items to the Header Control](../mfc/adding-items-to-the-header-control.md).  
  
## <a name="see-also"></a>See Also  
 [Using CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Controls](../mfc/controls-mfc.md)


