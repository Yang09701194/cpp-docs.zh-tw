---
title: Testing Internet Applications | Microsoft Docs
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
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
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
ms.openlocfilehash: 1bdf3922311d334eecece5fefbd7573f6dffab26
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="testing-internet-applications"></a>Testing Internet Applications
There are some unique testing challenges on the Internet, especially for applications running on a Web server. Your initial testing will probably be done using a single-user client connecting to a test server. This will be useful for debugging your code.  
  
 You will also want to test under real conditions: with multiple clients connected over high-speed connections as well as low-speed serial lines, including modem connections. It can be difficult to simulate real conditions, but it is certainly worth spending time designing possible scenarios and executing them. If possible, you will also want to use tools to do capacity and stress testing. Certain classes of bugs, such as timing bugs, are difficult to find and to reproduce.  
  
 One of the challenges of Internet programming is its visibility. Many accesses to your site may slow down your server. You want your server to degrade gracefully. You want to prevent anything that could be destructive to a user's computer if your application fails (for example, corruption of data while writing to the registry or while writing cookies on the client).  
  
## <a name="see-also"></a>See Also  
 [MFC Internet Programming Tasks](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programming Basics](../mfc/mfc-internet-programming-basics.md)


