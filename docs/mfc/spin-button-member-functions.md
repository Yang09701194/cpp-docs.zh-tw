---
title: Spin Button Member Functions | Microsoft Docs
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
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
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
ms.openlocfilehash: 5582767fb0a68f41664499bdb31b5ae06c3379cf
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="spin-button-member-functions"></a>Spin Button Member Functions
There are several member functions available for the spin control ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Use these functions to change the following attributes of the spin button.  
  
-   **Acceleration** You can adjust the rate at which the position changes when the user holds down the arrow button. To work with acceleration, use the [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) and [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) member functions.  
  
-   **Base** You can change the base (either 10 or 16) used to display the position in the caption of the buddy window. To work with the base, use the [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) and [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) member functions.  
  
-   **Buddy Window** You can dynamically set the buddy window. To query or change which control is the buddy window, use the [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) and [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) member functions.  
  
-   **Position** You can query and change the position. To work directly with position, use the [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) and [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) member functions. Since the caption of the buddy control may have changed (for example, in the case that the buddy is an edit control), `GetPos` retrieves the current caption and adjusts the position accordingly.  
  
-   **Range** You can change the maximum and minimum positions for the spin button. By default, the maximum is set to 0, and the minimum is set to 100. Since the default maximum is less than the default minimum, the actions of the arrow buttons is counter-intuitive. Typically, you will set the range using the [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) member function. To query the range use [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).  
  
## <a name="see-also"></a>See Also  
 [Using CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Controls](../mfc/controls-mfc.md)


