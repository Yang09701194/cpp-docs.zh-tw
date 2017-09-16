---
title: Frame-Window Styles (C++) | Microsoft Docs
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
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
caps.latest.revision: 8
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
ms.openlocfilehash: 69905342d643c58727dd513451e87285b44f9d8f
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="frame-window-styles-c"></a>Frame-Window Styles (C++)
The frame windows you get with the framework are suitable for most programs, but you can gain additional flexibility by using the advanced functions [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) and the MFC global function [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` is a member function of `CWnd`.  
  
 If you apply the **WS_HSCROLL** and **WS_VSCROLL** styles to the main frame window, they are instead applied to the **MDICLIENT** window so users can scroll the **MDICLIENT** area.  
  
 If the window's **FWS_ADDTOTITLE** style bit is set (which it is by default), the view tells the frame window what title to display in the window's title bar based on the view's document name.  
  
## <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Managing MDI child windows (MDICLIENT)](../mfc/managing-mdi-child-windows.md), the window within an MDI frame that contains the MDI child windows  
  
-   [Changing the styles of a window created by MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Window styles](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
## <a name="see-also"></a>See Also  
 [Frame Windows](../mfc/frame-windows.md)


