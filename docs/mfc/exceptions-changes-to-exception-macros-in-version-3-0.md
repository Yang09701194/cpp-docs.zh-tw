---
title: 'Exceptions: Changes to Exception Macros in Version 3.0 | Microsoft Docs'
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
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
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
ms.openlocfilehash: d3046dae0bad83d8fffc98e5c93573c4efb9d919
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Exceptions: Changes to Exception Macros in Version 3.0
This is an advanced topic.  
  
 In MFC version 3.0 and later, the exception-handling macros have been changed to use C++ exceptions. This article tells how those changes can affect the behavior of existing code that uses the macros.  
  
 This article covers the following topics:  
  
-   [Exception types and the CATCH macro](#_core_exception_types_and_the_catch_macro)  
  
-   [Re-throwing exceptions](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a> Exception Types and the CATCH Macro  
 In earlier versions of MFC, the **CATCH** macro used MFC run-time type information to determine an exception's type; the exception's type is determined, in other words, at the catch site. With C++ exceptions, however, the exception's type is always determined at the throw site by the type of the exception object that is thrown. This will cause incompatibilities in the rare case where the type of the pointer to the thrown object differs from the type of the thrown object.  
  
 The following example illustrates the consequence of this difference between MFC version 3.0 and earlier versions:  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 This code behaves differently in version 3.0 because control always passes to the first **catch** block with a matching exception-declaration. The result of the throw expression  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 is thrown as a **CException\***, even though it is constructed as a **CCustomException**. The **CATCH** macro in MFC versions 2.5 and earlier uses `CObject::IsKindOf` to test the type at run time. Because the expression  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 is true, the first catch block catches the exception. In version 3.0, which uses C++ exceptions to implement many of the exception-handling macros, the second catch block matches the thrown `CException`.  
  
 Code like this is uncommon. It usually appears when an exception object is passed to another function that accepts a generic **CException\***, performs "pre-throw" processing, and finally throws the exception.  
  
 To work around this problem, move the throw expression from the function to the calling code and throw an exception of the actual type known to the compiler at the time the exception is generated.  
  
##  <a name="_core_re.2d.throwing_exceptions"></a> Re-Throwing Exceptions  
 A catch block cannot throw the same exception pointer that it caught.  
  
 For example, this code was valid in previous versions, but will have unexpected results with version 3.0:  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 Using **THROW** in the catch block causes the pointer `e` to be deleted, so that the outer catch site will receive an invalid pointer. Use `THROW_LAST` to re-throw `e`.  
  
 For more information, see [Exceptions: Catching and Deleting Exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>See Also  
 [Exception Handling](../mfc/exception-handling-in-mfc.md)


