---
title: Providing Flicker-Free Activation | Microsoft Docs
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
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
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
ms.openlocfilehash: 3a0fa52ddc550194c4ebd968742236ef404ab0d9
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="providing-flicker-free-activation"></a>Providing Flicker-Free Activation
If your control draws itself identically in the inactive and active states (and does not use windowless activation), you can eliminate the drawing operations and the accompanying visual flicker that normally occur when making the transition between the inactive and active states. To do this, include the **noFlickerActivate** flag in the set of flags returned by [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). For example:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 The code to include this flag is automatically generated if you select the **Flicker-Free activation** option on the [Control Settings](../mfc/reference/control-settings-mfc-activex-control-wizard.md) page when creating your control with the MFC ActiveX Control Wizard.  
  
 If you are using windowless activation, this optimization has no effect.  
  
## <a name="see-also"></a>See Also  
 [MFC ActiveX Controls: Optimization](../mfc/mfc-activex-controls-optimization.md)


