---
title: Windows Sockets Classes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.net
dev_langs:
- C++
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
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
ms.openlocfilehash: 1d63612f9ef9c6587c6e08b3e4a56ce6c25e2c4d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="windows-sockets-classes"></a>Windows Sockets Classes
Windows Sockets provide a network protocol-independent way to communicate between two computers. These sockets can be synchronous (your program waits until the communication is done) or asynchronous (your program continues running while the communication is going on).  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Encapsulates the Windows Sockets API in a thin wrapper.  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 Higher level abstraction derived from `CAsyncSocket`. It operates synchronously.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Provides a `CFile` interface to a Windows Socket.  
  
## <a name="see-also"></a>See Also  
 [Class Overview](../mfc/class-library-overview.md)


