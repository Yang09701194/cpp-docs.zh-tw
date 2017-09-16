---
title: OLE Control Classes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
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
ms.openlocfilehash: a81de0a104d188f50c112d9f199ca04e315af920
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="ole-control-classes"></a>OLE Control Classes
These are the primary classes you use when writing OLE controls. The `COleControlModule` class in an OLE control module is like the [CWinApp](../mfc/reference/cwinapp-class.md) class in an application. Each module implements one or more OLE controls; these controls are represented by `COleControl` objects. These controls communicate with their containers using `CConnectionPoint` objects.  
  
 The `CPictureHolder` and `CFontHolder` classes encapsulate COM interfaces for pictures and fonts, while the `COlePropertyPage` and `CPropExchange` classes help you implement property pages and property persistence for your control.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 Replaces the `CWinApp` class for your OLE control module. Derive from the `COleControlModule` class to develop an OLE control module object. It provides member functions for initializing your OLE control's module.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 Derive from the `COleControl` class to develop an OLE control. Derived from `CWnd`, this class inherits all the functionality of a Windows window object plus additional OLE-specific functionality, such as event firing and the ability to support methods and properties.  
  
 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)  
 The `CConnectionPoint` class defines a special type of interface used to communicate with other OLE objects, called a connection point. A connection point implements an outgoing interface that is able to initiate actions on other objects, such as firing events and change notifications.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Encapsulates the functionality of a Windows picture object and the `IPicture` COM interface; used to implement the custom Picture property of an OLE control.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Encapsulates the functionality of a Windows font object and the `IFont` COM interface; used to implement the stock Font property of an OLE control.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Displays the properties of an OLE control in a graphical interface, similar to a dialog box.  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 Supports the implementation of property persistence for your OLE controls. Analogous to [CDataExchange](../mfc/reference/cdataexchange-class.md) for dialog boxes.  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 Takes a moniker, or a string representation that it can make into a moniker, and binds it synchronously to the stream for which the moniker is a name.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 Works similarly to `CMonikerFile`; however, it binds the moniker asynchronously to the stream for which the moniker is a name.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 Implements an OLE control property that can be loaded asynchronously.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 Implements an OLE control property transferred asynchronously and cached in a memory file.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Allows an Active document to receive commands that originate in its container's user interface (such as FileNew, Open, Print, and so on), and allows a container to receive commands that originate in the Active document's user interface.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 Works with arrays of arbitrary type and dimension.  
  
## <a name="see-also"></a>See Also  
 [Class Overview](../mfc/class-library-overview.md)


