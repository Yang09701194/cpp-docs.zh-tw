---
title: Reading and Writing Files | Microsoft Docs
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
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
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
ms.openlocfilehash: 8ed13b13d140d6e90a758183b62958145959cc3a
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="reading-and-writing-files"></a>Reading and Writing Files
If you've used the C run-time library file-handling functions, MFC reading and writing operations will appear familiar. This article describes reading directly from and writing directly to a `CFile` object. You can also do buffered file I/O with the [CArchive](../mfc/reference/carchive-class.md) class.  
  
#### <a name="to-read-from-and-write-to-the-file"></a>To read from and write to the file  
  
1.  Use the **Read** and **Write** member functions to read and write data in the file.  
  
     -or-  
  
2.  The `Seek` member function is also available for moving to a specific offset within the file.  
  
 **Read** takes a pointer to a buffer and the number of bytes to read and returns the actual number of bytes that were read. If the required number of bytes could not be read because end-of-file (EOF) is reached, the actual number of bytes read is returned. If any read error occurs, an exception is thrown. **Write** is similar to **Read**, but the number of bytes written is not returned. If a write error occurs, including not writing all the bytes specified, an exception is thrown. If you have a valid `CFile` object, you can read from it or write to it as shown in the following example:  
  
 [!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  You should normally carry out input/output operations within a **try**/**catch** exception handling block. For more information, see [Exception Handling (MFC)](../mfc/exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>See Also  
 [Files](../mfc/files-in-mfc.md)


