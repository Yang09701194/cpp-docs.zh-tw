---
title: Building on the Framework | Microsoft Docs
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
- application-specific classes [MFC]
- application framework [MFC], building applications
- applications [MFC]
- MFC, application development
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
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
ms.openlocfilehash: 14e4e98f27711fcc2b7f022d452b99f3a55969c6
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="building-on-the-framework"></a>Building on the Framework
Your role in configuring an application with the MFC framework is to supply the application-specific source code and to connect the components by defining what messages and commands to which they respond. You use the C++ language and standard C++ techniques to derive your own application-specific classes from those supplied by the class library and to override and augment the base class's behavior.  
  
 In related topics, the following tables describe the general sequence of operations you will typically follow and your responsibilities versus the framework's responsibilities:  
  
-   [Sequence for Building an Application with the Framework](../mfc/sequence-of-operations-for-building-mfc-applications.md)  
  
-   [Sequence of Operations for Creating OLE Applications](../mfc/sequence-of-operations-for-creating-ole-applications.md)  
  
-   [Sequence of Operations for Creating ActiveX Controls](../mfc/sequence-of-operations-for-creating-activex-controls.md)  
  
-   [Sequence of Operations for Creating Database Applications](../mfc/sequence-of-operations-for-creating-database-applications.md)  
  
 For the most part, you can follow these tables as a sequence of steps for creating an MFC application, although some of the steps are alternative options. For example, most applications use one type of view class from the several types available.  
  
## <a name="see-also"></a>See Also  
 [General MFC Topics](../mfc/general-mfc-topics.md)


