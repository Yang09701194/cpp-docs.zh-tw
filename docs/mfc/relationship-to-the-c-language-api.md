---
title: Relationship to the C-Language API | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
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
ms.openlocfilehash: 789064722f019a3f31fd4e30510b2b45682b7f21
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="relationship-to-the-c-language-api"></a>Relationship to the C-Language API
The single characteristic that sets the Microsoft Foundation Class (MFC) Library apart from other class libraries for Windows is the very close mapping to the Windows API written in the C language. Further, you can generally mix calls to the class library freely with direct calls to the Windows API. This direct access does not, however, imply that the classes are a complete replacement for that API. Developers must still occasionally make direct calls to some Windows functions, such as [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) and [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), for example. A Windows function is wrapped by a class member function only when there is a clear advantage to doing so.  
  
 Because you sometimes need to make native Windows function calls, you should have access to the C-language Windows API documentation. This documentation is included with Microsoft Visual C++.  
  
> [!NOTE]
>  For an overview of how the MFC Library framework operates, see [Using the Classes to Write Applications for Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>See Also  
 [General Class Design Philosophy](../mfc/general-class-design-philosophy.md)

