---
title: Manipulating the Progress Control | Microsoft Docs
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
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
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
ms.openlocfilehash: 82c8e32789f396a371af38c372d622d1405024f4
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="manipulating-the-progress-control"></a>Manipulating the Progress Control
There are three ways to change the current position of a progress control ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).  
  
-   The position can be changed by a preset increment amount.  
  
-   The position can be changed by an arbitrary amount.  
  
-   The position can be changed to a specific value.  
  
### <a name="to-change-the-position-by-a-preset-amount"></a>To change the position by a preset amount  
  
1.  Use the [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) member function to set the increment amount. By default, this value is 10. This value is typically set as one of the initial settings for the control. The step value can be negative.  
  
2.  Use the [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) member function to increment the position. This causes the control to redraw itself.  
  
    > [!NOTE]
    >  `StepIt` will cause the position to wrap. For example, given a range of 1 -100, a step of 20, and a position of 90, `StepIt` will set the position to 10.  
  
### <a name="to-change-the-position-by-an-arbitrary-amount"></a>To change the position by an arbitrary amount  
  
1.  Use the [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) member function to change the position. `OffsetPos` will accept negative values.  
  
    > [!NOTE]
    >  `OffsetPos`, unlike `StepIt`, will not wrap the position. The new position is adjusted to remain within the range.  
  
### <a name="to-change-the-position-to-a-specific-value"></a>To change the position to a specific value  
  
1.  Use the [SetPos](../mfc/reference/cprogressctrl-class.md#setpos) member function to set the position to a specific value. If necessary, the new position is adjusted to be within the range.  
  
 Typically, the progress control is used solely for output. To get the current position without specifying a new value, use [GetPos](../mfc/reference/cprogressctrl-class.md#getpos).  
  
## <a name="see-also"></a>See Also  
 [Using CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Controls](../mfc/controls-mfc.md)


