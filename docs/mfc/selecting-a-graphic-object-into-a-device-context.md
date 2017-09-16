---
title: Selecting a Graphic Object into a Device Context | Microsoft Docs
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
- graphic objects [MFC], selecting into device context
- SelectObject method [MFC]
- GDI objects [MFC], device contexts
- lifetime, graphic objects [MFC]
- device contexts, selecting graphic objects into
- device contexts, graphic objects [MFC]
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
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
ms.openlocfilehash: 4c9d3aaa2a3580be476f750d31c24ee61ddd6dbb
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="selecting-a-graphic-object-into-a-device-context"></a>Selecting a Graphic Object into a Device Context
This topic applies to using graphic objects in a window's device context. After you [create a drawing object](../mfc/one-stage-and-two-stage-construction-of-objects.md), you must select it into the device context in place of the default object stored there:  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/cpp/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## <a name="lifetime-of-graphic-objects"></a>Lifetime of Graphic Objects  
 The graphic object returned by [SelectObject](../mfc/reference/cdc-class.md#selectobject) is "temporary." That is, it will be deleted by the [OnIdle](../mfc/reference/cwinapp-class.md#onidle) member function of class `CWinApp` the next time the program gets idle time. As long as you use the object returned by `SelectObject` in a single function without returning control to the main message loop, you will have no problem.  
  
### <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Graphic objects](../mfc/graphic-objects.md)  
  
-   [One-stage and two-stage construction of graphic objects](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Device contexts](../mfc/device-contexts.md)  
  
-   [Drawing in a View](../mfc/drawing-in-a-view.md)  
  
## <a name="see-also"></a>See Also  
 [Graphic Objects](../mfc/graphic-objects.md)


