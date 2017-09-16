---
title: Common Dialog Classes | Microsoft Docs
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
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
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
ms.openlocfilehash: 0811c6b121aa86f09f3656b1061ff4aadbefd0a1
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="common-dialog-classes"></a>Common Dialog Classes
In addition to class [CDialog](../mfc/reference/cdialog-class.md), MFC supplies several classes derived from `CDialog` that encapsulate commonly used dialog boxes, as shown in the following table. The dialog boxes encapsulated are called the "common dialog boxes" and are part of the Windows common dialog library (COMMDLG.DLL). The dialog-template resources and code for these classes are provided in the Windows common dialog boxes that are part of Windows versions 3.1 and later.  
  
### <a name="common-dialog-classes"></a>Common Dialog Classes  
  
|Derived dialog class|Purpose|  
|--------------------------|-------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Lets user select colors.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Lets user select a filename to open or to save.|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Lets user initiate a find or replace operation in a text file.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Lets user specify a font.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Lets user specify information for a print job.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 2000 print property sheet.|  
  
 For more information about the common dialog classes, see the individual class names in the *MFC Reference*. MFC also supplies a number of standard dialog classes used for OLE. For information about these classes, see the base class, [COleDialog](../mfc/reference/coledialog-class.md), in the *MFC Reference*.  
  
 Three other classes in MFC have dialog-like characteristics. For information about classes [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), and [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), see the classes in the *MFC Reference*. For information about class [CDialogBar](../mfc/reference/cdialogbar-class.md), see [Dialog Bars](../mfc/dialog-bars.md).  
  
## <a name="see-also"></a>See Also  
 [Dialog Boxes](../mfc/dialog-boxes.md)   
 [Life Cycle of a Dialog Box](../mfc/life-cycle-of-a-dialog-box.md)   
 [Dialog Boxes in OLE](../mfc/dialog-boxes-in-ole.md)


