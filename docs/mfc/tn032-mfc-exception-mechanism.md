---
title: 'TN032: MFC Exception Mechanism | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
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
ms.openlocfilehash: 86c149585d9ea7905ace80f7a6aad51eab5dc6dc
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC Exception Mechanism
Previous versions of Visual C++ did not support the standard C++ exception mechanism, and MFC provided macros **TRY/CATCH/THROW** that were used instead. This version of Visual C++ fully supports C++ exceptions. This note covered some of the advanced implementation details of the previous macros including how to automatically cleanup stack based objects. Because C++ exceptions support stack unwinding by default, this technical note is no longer necessary.  
  
 Refer to [Exceptions: Using MFC Macros and C++ Exceptions](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) for more information on the differences between the MFC macros and the new C++ keywords.  
  
## <a name="see-also"></a>See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)


