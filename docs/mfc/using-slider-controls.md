---
title: Using Slider Controls | Microsoft Docs
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
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
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
ms.openlocfilehash: 27b4b5b8bb454a5b4bee0fdd09b6ff8698651761
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="using-slider-controls"></a>Using Slider Controls
Typical usage of an slider control follows the pattern below:  
  
-   The control is created. If the control is specified in a dialog box template, creation is automatic when the dialog box is created. (You should have a [CSliderCtrl](../mfc/reference/csliderctrl-class.md) member in your dialog class that corresponds to the slider control.) Alternatively, you can use the [Create](../mfc/reference/csliderctrl-class.md#create) member function to create the control as a child window of any window.  
  
-   Call the various Set member functions to set values for the control. Changes that you can make include setting the minimum and maximum positions for the slider, drawing tick marks, setting a selection range, and repositioning the slider. For controls in a dialog box, a good time to do this is in the dialog's [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) function.  
  
-   As the user interacts with the control, it will send various notification messages. You can extract the slider value from the control by calling the [GetPos](../mfc/reference/csliderctrl-class.md#getpos) member function.  
  
-   When you're done with the control, you need to make sure it's properly destroyed. If the slider control is in a dialog box, it and the `CSliderCtrl` object will be destroyed automatically. If not, you need to ensure that both the control and the `CSliderCtrl` object are properly destroyed.  
  
## <a name="see-also"></a>See Also  
 [Using CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Controls](../mfc/controls-mfc.md)


