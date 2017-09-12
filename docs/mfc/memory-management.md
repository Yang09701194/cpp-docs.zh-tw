---
title: Memory Management | Microsoft Docs
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
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
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
ms.openlocfilehash: cf494a6f394c2a8104365112260e1d86cdedadcd
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="memory-management"></a>Memory Management
This group of articles describes how to take advantage of the general-purpose services of the Microsoft Foundation Class Library (MFC) related to memory management. Memory allocation can be divided into two main categories: frame allocations and heap allocations.  
  
 One main difference between the two allocation techniques is that with frame allocation you typically work with the actual memory block itself, while with heap allocation you are always given a pointer to the memory block. Another major difference between the two schemes is that frame objects are automatically deleted, while heap objects must be explicitly deleted by the programmer.  
  
 For non-MFC information about memory management in programs for Windows, see [Memory Management](http://msdn.microsoft.com/library/windows/desktop/aa366779) in the Windows SDK.  
  
## <a name="what-do-you-want-to-know-more-about"></a>What do you want to know more about  
  
-   [Frame allocation](../mfc/memory-management-frame-allocation.md)  
  
-   [Heap allocation](../mfc/memory-management-heap-allocation.md)  
  
-   [Allocating memory for an array](../mfc/memory-management-examples.md)  
  
-   [Deallocating memory for an array from the heap](../mfc/memory-management-examples.md)  
  
-   [Allocating memory for a data structure](../mfc/memory-management-examples.md)  
  
-   [Allocating memory for an object](../mfc/memory-management-examples.md)  
  
-   [Resizable memory blocks](../mfc/memory-management-resizable-memory-blocks.md)  
  
## <a name="see-also"></a>See Also  
 [Concepts](../mfc/mfc-concepts.md)   
 [General MFC Topics](../mfc/general-mfc-topics.md)


