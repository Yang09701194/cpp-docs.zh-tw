---
title: OLE in MFC | Microsoft Docs
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
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
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
ms.openlocfilehash: 3346c3f6d1c2fd02d8a3cd21230d66dd13e0b9be
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="ole-in-mfc"></a>OLE in MFC
These articles explain the fundamentals of OLE programming using MFC. MFC provides the easiest way to write programs that use OLE:  
  
-   To use OLE visual editing (in-place activation).  
  
-   To work as OLE containers or servers.  
  
-   To implement drag-and-drop functionality.  
  
-   To work with date and time data.  
  
-   To manage the state data of MFC modules, including exported DLL function entry points, OLE/COM interface entry points, and window procedure entry points.  
  
 You can also use [Automation](../mfc/automation.md) or [Remote Automation](../mfc/remote-automation.md) to operate another program from your program.  
  
> [!NOTE]
>  The term OLE denotes the technologies associated with linking and embedding, including OLE containers, OLE servers, OLE items, in-place activation (or visual editing), trackers, drag and drop, and menu merging. The term Active applies to the Component Object Model (COM) and COM-based objects such as ActiveX controls. OLE Automation is now called Automation.  
  
## <a name="in-this-section"></a>In This Section  
 [OLE Background](../mfc/ole-background.md)  
 Discusses OLE and provides conceptual information about how it works.  
  
 [Activation](../mfc/activation-cpp.md)  
 Describes the role of activation in editing OLE items.  
  
 [Containers](../mfc/containers.md)  
 Provides links to using containers in OLE.  
  
 [Data Objects and Data Sources](../mfc/data-objects-and-data-sources-ole.md)  
 Provides links to topics discussing the use of the `COleDataObject` and `COleDataSource` classes.  
  
 [Drag and Drop](../mfc/drag-and-drop-ole.md)  
 Discusses using copying and pasting with OLE.  
  
 [OLE Menus and Resources](../mfc/menus-and-resources-ole.md)  
 Explains the use of menus and resources in MFC OLE document applications.  
  
 [Registration](../mfc/registration.md)  
 Discusses server installation and initialization.  
  
 [Servers](../mfc/servers.md)  
 Describes how to create OLE items (or components) for use by container applications.  
  
 [Trackers](../mfc/trackers.md)  
 Provides information about the `CRectTracker` class, which provides a graphical interface to enable users to interact with OLE client items.  
  
## <a name="related-sections"></a>Related Sections  
 [Connection Points](../mfc/connection-points.md)  
 Explains how to implement connection points (formerly known as OLE connection points) using the MFC classes `CCmdTarget` and `CConnectionPoint`.  
  
 [Container/Server COM Components](../mfc/containers-advanced-features.md)  
 Describes the steps necessary to incorporate optional advanced features into existing container applications.  
  
 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 Describes using OLE without MFC.  
  
## <a name="see-also"></a>See Also  
 [Concepts](../mfc/mfc-concepts.md)


