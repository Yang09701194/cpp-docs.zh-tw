---
title: Using an Animation Control | Microsoft Docs
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
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
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
ms.openlocfilehash: e7555102fdfdb3cbe1405b23a1acde25178567bb
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="using-an-animation-control"></a>Using an Animation Control
Typical usage of an animation control follows the pattern below:  
  
-   The control is created. If the control is specified in a dialog box template, creation is automatic when the dialog box is created. (You should have a [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) member in your dialog class that corresponds to the animation control.) Alternatively, you can use the [Create](../mfc/reference/canimatectrl-class.md#create) member function to create the control as a child window of any window.  
  
-   Load an AVI clip into the animation control by calling the [Open](../mfc/reference/canimatectrl-class.md#open) member function. If your animation control is in a dialog box, a good place to do this is in the dialog class's [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) function.  
  
-   Play the clip by calling the [Play](../mfc/reference/canimatectrl-class.md#play) member function. If your animation control is in a dialog box, a good place to do this is in the dialog class's **OnInitDialog** function. Calling **Play** is not necessary if the animation control has the `ACS_AUTOPLAY` style set.  
  
-   If you want to display portions of the clip or play it frame by frame, use the `Seek` member function. To stop a clip that is playing, use the `Stop` member function.  
  
-   If you are not going to destroy the control right away, remove the clip from memory by calling the **Close** member function.  
  
-   If the animation control is in a dialog box, it and the `CAnimateCtrl` object will be destroyed automatically. If not, you need to ensure that both the control and the `CAnimateCtrl` object are properly destroyed. Destroying the control automatically closes the AVI clip.  
  
## <a name="see-also"></a>See Also  
 [Using CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Controls](../mfc/controls-mfc.md)


