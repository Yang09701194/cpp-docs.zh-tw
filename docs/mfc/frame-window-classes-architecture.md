---
title: Frame Window Classes (Architecture) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.frame
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: 9
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
ms.openlocfilehash: 66f5c9f7ab9d8e72fb357accf84eb93bf44595ea
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="frame-window-classes-architecture"></a>Frame Window Classes (Architecture)
In document/view architecture, frame windows are windows that contain a view window. They also support having control bars attached to them.  
  
 In multiple document interface (MDI) applications, the main window is derived from `CMDIFrameWnd`. It indirectly contains the documents' frames, which are `CMDIChildWnd` objects. The `CMDIChildWnd` objects, in turn, contain the documents' views.  
  
 In single document interface (SDI) applications, the main window, derived from `CFrameWnd`, contains the view of the current document.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 The base class for an SDI application's main frame window. Also the base class for all other frame window classes.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 The base class for an MDI application's main frame window.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 The base class for an MDI application's document frame windows.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Provides the frame window for a view when a server document is being edited in place.  
  
## <a name="see-also"></a>See Also  
 [Class Overview](../mfc/class-library-overview.md)


