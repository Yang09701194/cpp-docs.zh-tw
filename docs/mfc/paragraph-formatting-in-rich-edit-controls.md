---
title: Paragraph Formatting in Rich Edit Controls | Microsoft Docs
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
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
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
ms.openlocfilehash: 12424417c0d2ff6ca8d48a047ee2d44b29c06a3d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Paragraph Formatting in Rich Edit Controls
You can use member functions of the rich edit control ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) to format paragraphs and to retrieve formatting information. Paragraph formatting attributes include alignment, tabs, indents, and numbering.  
  
 You can apply paragraph formatting by using the [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) member function. To determine the current paragraph formatting for the selected text, use the [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) member function. The [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) structure is used with these member functions to specify paragraph attributes. One of the important members of **PARAFORMAT** is **dwMask**. In `SetParaFormat`, **dwMask** specifies which paragraph attributes will be set by this function call. `GetParaFormat` reports the attributes of the first paragraph in the selection; **dwMask** specifies the attributes that are consistent throughout the selection.  
  
## <a name="see-also"></a>See Also  
 [Using CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Controls](../mfc/controls-mfc.md)


