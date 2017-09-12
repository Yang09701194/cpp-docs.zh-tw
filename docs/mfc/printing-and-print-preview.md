---
title: Printing and Print Preview | Microsoft Docs
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
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 11
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
ms.openlocfilehash: fc0dd2a387ebdcfe43d68afdd894cf92fdd94827
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="printing-and-print-preview"></a>Printing and Print Preview
MFC supports printing and print preview for your program's documents via class [CView](../mfc/reference/cview-class.md). For basic printing and print preview, simply override your view class's [OnDraw](../mfc/reference/cview-class.md#ondraw) member function, which you must do anyway. That function can draw to the view on the screen, to a printer device context for an actual printer, or to a device context that simulates your printer on the screen.  
  
 You can also add code to manage multipage document printing and preview, to paginate your printed documents, and to add headers and footers to them.  
  
 This family of articles explains how printing is implemented in the Microsoft Foundation Class Library (MFC) and how to take advantage of the printing architecture already built into the framework. The articles also explain how MFC supports easy implementation of print preview functionality and how you can use and modify that functionality.  
  
## <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Printing](../mfc/printing.md)  
  
-   [Print preview architecture](../mfc/print-preview-architecture.md)  
  
-   [Sample](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>See Also  
 [User Interface Elements](../mfc/user-interface-elements-mfc.md)

