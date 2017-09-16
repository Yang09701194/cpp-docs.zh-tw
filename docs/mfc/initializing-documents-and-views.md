---
title: Initializing Documents and Views | Microsoft Docs
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
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
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
ms.openlocfilehash: 9214fc1f08e0b22a2660e542689e3dd4fb4002f8
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="initializing-documents-and-views"></a>Initializing Documents and Views
Documents are created in two different ways, so your document class must support both ways. First, the user can create a new, empty document with the File New command. In that case, initialize the document in your override of the [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) member function of class [CDocument](../mfc/reference/cdocument-class.md). Second, the user can use the Open command on the File menu to create a new document whose contents are read from a file. In that case, initialize the document in your override of the [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) member function of class **CDocument**. If both initializations are the same, you can call a common member function from both overrides, or `OnOpenDocument` can call `OnNewDocument` to initialize a clean document and then finish the open operation.  
  
 Views are created after their documents are created. The best time to initialize a view is after the framework has finished creating the document, frame window, and view. You can initialize your view by overriding the [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) member function of [CView](../mfc/reference/cview-class.md). If you need to reinitialize or adjust anything each time the document changes, you can override [OnUpdate](../mfc/reference/cview-class.md#onupdate).  
  
## <a name="see-also"></a>See Also  
 [Initializing and Cleaning Up Documents and Views](../mfc/initializing-and-cleaning-up-documents-and-views.md)


