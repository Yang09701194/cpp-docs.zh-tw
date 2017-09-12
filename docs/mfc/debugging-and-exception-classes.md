---
title: Debugging and Exception Classes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
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
ms.openlocfilehash: 57cdc402a29c557c37a5f43b0634fd4fb2c8a168
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="debugging-and-exception-classes"></a>Debugging and Exception Classes
These classes provide support for debugging dynamic memory allocation and for passing exception information from the function where the exception is thrown to the function where it is caught.  
  
 Use classes [CDumpContext](../mfc/reference/cdumpcontext-class.md) and [CMemoryState](../mfc/reference/cmemorystate-structure.md) during development to assist with debugging, as described in [Debugging MFC Applications](/visualstudio/debugger/mfc-debugging-techniques). Use [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) to determine the class of any object at run time, as described in the article [Accessing Run-Time Class Information](../mfc/accessing-run-time-class-information.md). The framework uses `CRuntimeClass` to create objects of a particular class dynamically.  
  
## <a name="see-also"></a>See Also  
 [Class Overview](../mfc/class-library-overview.md)


