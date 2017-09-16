---
title: Dragging and Dropping Files in a Frame Window | Microsoft Docs
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
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
caps.latest.revision: 11
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
ms.openlocfilehash: 337a191a27737b428ddea4bce9d21d3487c18942
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>Dragging and Dropping Files in a Frame Window
The frame window manages a relationship with File Explorer or File Manager.  
  
 By adding a few initializing calls in your override of the `CWinApp` member function `InitInstance`, as described in [CWinApp: The Application Class](../mfc/cwinapp-the-application-class.md), you can have your frame window indirectly open files dragged from File Explorer or File Manager and dropped in the frame window. See [File Manager Drag and Drop](../mfc/special-cwinapp-services.md).  
  
## <a name="see-also"></a>See Also  
 [Using Frame Windows](../mfc/using-frame-windows.md)


