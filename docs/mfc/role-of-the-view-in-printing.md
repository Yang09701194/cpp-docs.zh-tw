---
title: Role of the View in Printing | Microsoft Docs
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
- views [MFC], printing
- OnDraw method [MFC], and printing
- printing [MFC], OnDraw method [MFC]
- printing [MFC], views
- CView class [MFC], role in printing
- printing views [MFC]
ms.assetid: 8d4a3c8e-1fce-4edc-b608-94cb5f3e487e
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
ms.openlocfilehash: 28d18718ca992c77d20416e63adb24c24cc6a647
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="role-of-the-view-in-printing"></a>Role of the View in Printing
Your view also plays two important roles in printing its associated document.  
  
 The view:  
  
-   Uses the same [OnDraw](../mfc/reference/cview-class.md#ondraw) code to draw on the printer as to draw on the screen.  
  
-   Manages dividing the document into pages for printing.  
  
 For more information about printing and about the view's role in printing, see [Printing and Print Preview](../mfc/printing-and-print-preview.md).  
  
## <a name="see-also"></a>See Also  
 [Using Views](../mfc/using-views.md)


