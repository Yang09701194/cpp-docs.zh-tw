---
title: Creating the Dialog Resource | Microsoft Docs
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
- dialog resources
- MFC dialog boxes [MFC], creating
- dialog templates [MFC], creating dialog resource
- templates [MFC], creating
- resources [MFC], creating dialog boxes
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 0b83bd33-14d3-4611-8129-fccdae18053e
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
ms.openlocfilehash: af33a71f914e5e7545d9719bf2f620f3feb4faa7
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="creating-the-dialog-resource"></a>Creating the Dialog Resource
To design the [dialog box](../mfc/dialog-boxes.md) and create the dialog resource, you use the [dialog editor](../windows/dialog-editor.md). In the dialog editor, you can:  
  
-   Adjust the size and location your dialog box will have when it appears.  
  
-   Drag various kinds of controls from a controls palette and drop them where you want them in the dialog box.  
  
-   Position the controls with alignment buttons on the toolbar.  
  
-   Test your dialog box by simulating the appearance and behavior it will have in your program. In Test mode, you can manipulate the dialog box's controls by typing text in text boxes, clicking pushbuttons, and so on.  
  
 When you finish, your dialog-template resource is stored in your application's resource script file. You can edit it later if needed. For a full description of how to create and edit dialog resources, see the [dialog editor](../windows/dialog-editor.md) topics. This technique is also used to create the dialog-template resources for [CFormView](../mfc/reference/cformview-class.md) and [CRecordView](../mfc/reference/crecordview-class.md) classes.  
  
 When the dialog box's appearance suits you, create a dialog class and map its messages, as discussed in [Creating a Dialog Class with Code Wizards](../mfc/creating-a-dialog-class-with-code-wizards.md).  
  
## <a name="see-also"></a>See Also  
 [Dialog Boxes](../mfc/dialog-boxes.md)   
 [Life Cycle of a Dialog Box](../mfc/life-cycle-of-a-dialog-box.md)


