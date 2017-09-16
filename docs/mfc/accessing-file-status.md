---
title: Accessing File Status | Microsoft Docs
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
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
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
ms.openlocfilehash: bb9f54784f7046bc73e33f8a53c9bb49956b12e6
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="accessing-file-status"></a>Accessing File Status
`CFile` also supports getting file status, including whether the file exists, creation and modification dates and times, logical size, and path.  
  
### <a name="to-get-file-status"></a>To get file status  
  
1.  Use the [CFile](../mfc/reference/cfile-class.md) class to get and set information about a file. One useful application is to use the `CFile` static member function **GetStatus** to determine if a file exists. **GetStatus** returns 0 if the specified file does not exist.  
  
 Thus, you could use the result of **GetStatus** to determine whether to use the **CFile::modeCreate** flag when opening a file, as shown by the following example:  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 For related information, see [Serialization](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>See Also  
 [Files](../mfc/files-in-mfc.md)


