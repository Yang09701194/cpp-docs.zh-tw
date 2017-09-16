---
title: Menus and Resources (OLE) | Microsoft Docs
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
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
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
ms.openlocfilehash: ca4f6b95f418e59610131a4b6fbf2f684074630e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="menus-and-resources-ole"></a>Menus and Resources (OLE)
This group of articles explains the use of menus and resources in MFC OLE document applications.  
  
 OLE visual editing places additional requirements on the menu and other resources provided by OLE document applications because there are a number of modes in which both container and server (component) applications can be started and used. For example, a full-server application can run in any of these three modes:  
  
-   Stand alone.  
  
-   In place, for editing an item within the context of a container.  
  
-   Open, for editing an item outside the context of its container, often in a separate window.  
  
 This requires three separate menu layouts, one for each possible mode of the application. Accelerator tables are also necessary for each new mode. A container application may or may not support in-place activation; if it does, it needs a new menu structure and associated accelerator tables.  
  
 In-place activation requires that the container and server applications must negotiate for menu, toolbar, and status bar space. All resources must be designed with this in mind. The article [Menus and Resources: Menu Merging](../mfc/menus-and-resources-menu-merging.md) covers this topic in detail.  
  
 Because of these issues, OLE document applications created with the application wizard can have up to four separate menus and accelerator table resources. These are used for the following reasons:  
  
|Resource name|Use|  
|-------------------|---------|  
|**IDR_MAINFRAME**|Used in an MDI application if no file is open, or in an SDI application regardless of open files. This is the standard menu used in non-OLE applications.|  
|**IDR_\<project>TYPE**|Used in an MDI application if files are open. Used when an application is running stand-alone. This is the standard menu used in non-OLE applications.|  
|**IDR_\<project>TYPE_SRVR_IP**|Used by the server or container when an object is open in place.|  
|**IDR_\<project>TYPE_SRVR_EMB**|Used by a server application if an object is opened without using in-place activation.|  
  
 Each of these resource names represents a menu and, usually, an accelerator table. A similar scheme should be used in MFC applications that are not created with the application wizard.  
  
 The following articles discuss topics related to containers, servers, and the menu merging necessary to implement in-place activation:  
  
-   [Menus and Resources: Container Additions](../mfc/menus-and-resources-container-additions.md)  
  
-   [Menus and Resources: Server Additions](../mfc/menus-and-resources-server-additions.md)  
  
-   [Menus and Resources: Menu Merging](../mfc/menus-and-resources-menu-merging.md)  
  
## <a name="see-also"></a>See Also  
 [OLE](../mfc/ole-in-mfc.md)


