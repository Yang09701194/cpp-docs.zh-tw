---
title: Creating and Displaying Dialog Boxes | Microsoft Docs
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
- modal dialog boxes [MFC], creating
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
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
ms.openlocfilehash: 0791b27a8ca62f6db80d759d22fde7d3eafa58a6
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="creating-and-displaying-dialog-boxes"></a>Creating and Displaying Dialog Boxes
Creating a dialog object is a two-phase operation. First, construct the dialog object, then create the dialog window. Modal and modeless dialog boxes differ somewhat in the process used to create and display them. The following table lists how modal and modeless dialog boxes are normally constructed and displayed.  
  
### <a name="dialog-creation"></a>Dialog Creation  
  
|Dialog type|How to create it|  
|-----------------|----------------------|  
|[Modeless](../mfc/creating-modeless-dialog-boxes.md)|Construct `CDialog`, then call **Create** member function.|  
|[Modal](../mfc/creating-modal-dialog-boxes.md)|Construct `CDialog`, then call `DoModal` member function.|  
  
 You can, if you want, create your dialog box from an [in-memory dialog template](../mfc/using-a-dialog-template-in-memory.md) that you have constructed rather than from a dialog template resource. This is an advanced topic, however.  
  
## <a name="see-also"></a>See Also  
 [Life Cycle of a Dialog Box](../mfc/life-cycle-of-a-dialog-box.md)


