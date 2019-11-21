---
title: 例外狀況：攔截及刪除例外狀況
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
ms.openlocfilehash: 0142ffddfb391ae8da878d9e5fe34629cf16cb52
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246697"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>例外狀況：攔截及刪除例外狀況

下列指示和範例示範如何攔截和刪除例外狀況。 For more information on the **try**, **catch**, and **throw** keywords, see [Modern C++ best practices for exceptions and error handling](../cpp/errors-and-exception-handling-modern-cpp.md).

您的例外狀況處理常式必須刪除其所處理的例外狀況物件，因為每當程式碼攔截例外狀況時，若無法刪除例外狀況就會導致記憶體流失。

Your **catch** block must delete an exception when:

- The **catch** block throws a new exception.

   當然，如果您再次擲回相同的例外狀況，則不得刪除例外狀況：

   [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Execution returns from within the **catch** block.

> [!NOTE]
>  When deleting a `CException`, use the `Delete` member function to delete the exception. Do not use the **delete** keyword, because it can fail if the exception is not on the heap.

#### <a name="to-catch-and-delete-exceptions"></a>攔截和刪除例外狀況

1. Use the **try** keyword to set up a **try** block. Execute any program statements that might throw an exception within a **try** block.

   Use the **catch** keyword to set up a **catch** block. Place exception-handling code in a **catch** block. The code in the **catch** block is executed only if the code within the **try** block throws an exception of the type specified in the **catch** statement.

   The following skeleton shows how **try** and **catch** blocks are normally arranged:

   [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

   When an exception is thrown, control passes to the first **catch** block whose exception-declaration matches the type of the exception. You can selectively handle different types of exceptions with sequential **catch** blocks as listed below:

   [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

For more information, see [Exceptions: Converting from MFC Exception Macros](../mfc/exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>請參閱

[例外狀況處理](../mfc/exception-handling-in-mfc.md)
