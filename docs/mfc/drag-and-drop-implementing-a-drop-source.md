---
title: 'Drag and Drop: Implementing a Drop Source | Microsoft Docs'
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
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
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
ms.openlocfilehash: f3bb2f7b11c3ce4d46f0dda53980c0c751ec41ef
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Drag and Drop: Implementing a Drop Source
This article explains how to get your application to provide data to a drag-and-drop operation.  
  
 Basic implementation of a drop source is relatively simple. The first step is to determine what events begin a drag operation. Recommended user interface guidelines define the beginning of a drag operation as the selection of data and a `WM_LBUTTONDOWN` event occurring on a point inside the selected data. The MFC OLE samples [OCLIENT](../visual-cpp-samples.md) and [HIERSVR](../visual-cpp-samples.md) follow these guidelines.  
  
 If your application is a container and the selected data is a linked or an embedded object of type `COleClientItem`, call its `DoDragDrop` member function. Otherwise, construct a `COleDataSource` object, initialize it with the selection, and call the data source object's `DoDragDrop` member function. If your application is a server, use `COleServerItem::DoDragDrop`. For information about customizing standard drag-and-drop behavior, see the article [Drag and Drop: Customizing](../mfc/drag-and-drop-customizing.md).  
  
 If `DoDragDrop` returns `DROPEFFECT_MOVE`, delete the source data from the source document immediately. No other return value from `DoDragDrop` has any effect on a drop source.  
  
 For more information, see:  
  
-   [Implementing a Drop Target](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Customizing Drag and Drop](../mfc/drag-and-drop-customizing.md)  
  
-   [Creating and Destroying OLE Data Objects and Data Sources](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Manipulating OLE Data Objects and Data Sources](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>See Also  
 [Drag and Drop (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)   
 [COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)   
 [CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)


