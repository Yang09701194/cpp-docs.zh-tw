---
title: Sequence of Operations for Creating OLE Applications | Microsoft Docs
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
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
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
ms.openlocfilehash: b52e194220ad1384def52e0a099fe82503bdf2a9
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>Sequence of Operations for Creating OLE Applications
The following table shows your role and the framework's role in creating OLE linking and embedding applications. These represent options available rather than a sequence of steps to perform.  
  
### <a name="creating-ole-applications"></a>Creating OLE Applications  
  
|Task|You do|The framework does|  
|----------|------------|------------------------|  
|Create a COM component.|Run the MFC Application Wizard. Choose **Full-server** or **Mini-server** in the **Compound Document Support** tab.|The framework generates a skeleton application with COM component capability enabled. All of the COM capability can be transferred to your existing application with only slight modification.|  
|Create a container application from scratch.|Run the MFC Application Wizard. Choose **Container** in the **Compound Document Support** tab. Using Class View, go to the source code editor. Fill in code for your COM handler functions.|The framework generates a skeleton application that can insert COM objects created by COM component (server) applications.|  
|Create an application that supports Automation from scratch.|Run the MFC Application Wizard. Choose **Automation** from the **Advanced Features** tab. Use Class View to expose methods and properties in your application for automation.|The framework generates a skeleton application that can be activated and automated by other applications.|  
  
## <a name="see-also"></a>See Also  
 [Building on the Framework](../mfc/building-on-the-framework.md)   
 [Sequence of Operations for Building MFC Applications](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Sequence of Operations for Creating ActiveX Controls](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Sequence of Operations for Creating Database Applications](../mfc/sequence-of-operations-for-creating-database-applications.md)


