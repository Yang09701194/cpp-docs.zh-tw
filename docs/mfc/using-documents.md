---
title: Using Documents | Microsoft Docs
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
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
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
ms.openlocfilehash: fc12ddaff980b92c5174b2de7a5f6a122e4f5a08
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="using-documents"></a>Using Documents
Working together, documents and views:  
  
-   Contain, manage, and display your application-specific [data](../mfc/managing-data-with-document-data-variables.md).  
  
-   Provide an interface consisting of [document data variables](../mfc/managing-data-with-document-data-variables.md) for manipulating the data.  
  
-   Participate in [writing and reading files](../mfc/serializing-data-to-and-from-files.md).  
  
-   Participate in [printing](../mfc/role-of-the-view-in-printing.md).  
  
-   [Handle](../mfc/handling-commands-in-the-document.md) most of your application's commands and messages.  
  
 The document is particularly involved in managing data. Store your data, normally, in document class member variables. The view uses these variables to access the data for display and update. The document's default serialization mechanism manages reading and writing the data to and from files. Documents can also handle commands (but not Windows messages other than **WM_COMMAND**).  
  
## <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Deriving a document class from CDocument](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Managing data with document data variables](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Serializing data to and from files](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Bypassing the serialization mechanism](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Handling commands in the document](../mfc/handling-commands-in-the-document.md)  
  
-   [The OnNewDocument member function](../mfc/reference/cdocument-class.md#onnewdocument)  
  
-   [The DeleteContents member function](../mfc/reference/cdocument-class.md#deletecontents)  
  
## <a name="see-also"></a>See Also  
 [Document/View Architecture](../mfc/document-view-architecture.md)


