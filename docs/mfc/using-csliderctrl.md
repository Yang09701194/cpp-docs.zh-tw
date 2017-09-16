---
title: Using CSliderCtrl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSliderCtrl
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls [MFC], using
ms.assetid: 242c7bcd-126e-4b9b-8f76-8082ad06fe73
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
ms.openlocfilehash: a942ef48c8916866d647e7b358ffa1a6b7e4829f
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="using-csliderctrl"></a>Using CSliderCtrl
The [CSliderCtrl](../mfc/reference/csliderctrl-class.md) class represents a slider control, which is also called a trackbar. A "slider control" is a window that contains a slider and optional tick marks. When the user moves the slider, using either the mouse or the arrow keys, the slider control sends notification messages to indicate the change.  
  
 Slider controls are useful when you want the user to select a discrete value or a set of consecutive values in a range. For example, you might use a slider control to allow the user to set the repeat rate of the keyboard by moving the slider to a given tick mark.  
  
 The slider in a slider control moves in increments that you specify when you create it. For example, if you specify that the slider control should have a range of five, the slider can only occupy six positions: a position at the left side of the slider control and one position for each increment in the range. Typically, each of these positions is identified by a tick mark.  
  
## <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Using Slider Controls](../mfc/using-slider-controls.md)  
  
-   [Slider Control Styles](../mfc/slider-control-styles.md)  
  
-   [Slider Control Member Functions](../mfc/slider-control-member-functions.md)  
  
-   [Slider Notification Messages](../mfc/slider-notification-messages.md)  
  
## <a name="see-also"></a>See Also  
 [Controls](../mfc/controls-mfc.md)


