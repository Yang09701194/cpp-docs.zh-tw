---
title: MFC Macros and Globals | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
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
ms.translationtype: MT
ms.sourcegitcommit: 4e0027c345e4d414e28e8232f9e9ced2b73f0add
ms.openlocfilehash: 077df418dfaea723965bb2a8876bceaf754a8346
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="mfc-macros-and-globals"></a>MFC Macros and Globals
The Microsoft Foundation Class Library can be divided into two major sections: (1) the MFC classes and (2) macros and globals. If a function or variable is not a member of a class, it is a global function or variable.  
  
 The MFC library and the Active Template Library (ATL) share string conversion macros. For more information, see [String Conversion Macros](../../atl/reference/string-conversion-macros.md) in the ATL documentation.  
  
 The MFC macros and globals offer functionality in the following categories.  
  
## <a name="general-mfc"></a>General MFC  
  
-   [Data types](data-types-mfc.md)  
  
-   [Type casting of MFC class objects](type-casting-of-mfc-class-objects.md)  
  
-   [Run-time object model services](run-time-object-model-services.md)  
  
-   [Diagnostic services](diagnostic-services.md)  
  
-   [Exception processing](exception-processing.md)  
  
-   [CString formatting and message-box display](cstring-formatting-and-message-box-display.md)  
  
-   [Message maps](message-map-macros-mfc.md)  

-   [Delegate and Interface Maps](delegate-and-interface-maps.md)

-   [Modules and DLLs](extension-dll-macros.md)
  
-   [Application information and management](application-information-and-management.md)  
  
-   [Standard command and window IDs](standard-command-and-window-ids.md)  
  
-   [Collection class helpers](collection-class-helpers.md)  
  
-   [Gray and dithered bitmap functions](gray-and-dithered-bitmap-functions.md)  
  
-   [Standard dialog data exchange (DDX) routines](standard-dialog-data-exchange-routines.md)  
  
-   [Standard dialog data validation (DDV) routines](standard-dialog-data-validation-routines.md)  
  
-   [AFX Messages](afx-messages.md)  
  
-   [ToolBar Control Styles](toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>Database  
  
-   [Record Field Exchange (RFX) functions](record-field-exchange-functions.md) and [Bulk Record Field Exchange (bulk RFX) functions](record-field-exchange-functions.md) for the MFC ODBC classes  
  
-   [Record field exchange (DFX) functions](record-field-exchange-functions.md) for the MFC DAO classes  
  
-   [Dialog data exchange (DDX) functions for CRecordView and CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC ODBC and DAO classes)  
  
-   [Dialog data exchange (DDX) functions for OLE controls](dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Macros and globals to aid in calling Open Database Connectivity (ODBC) API functions directly](database-macros-and-globals.md)  
  
-   [DAO database engine initialization and termination](dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>Internet  
  
-   [Internet URL parsing globals](internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML / DHTML Event Maps  
  
-   [DHTML dialog data exchange (DDX) helper macros](ddx-dhtml-helper-macros.md)  
  
-   [DHTML event maps](dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [OLE initialization](ole-initialization.md)  
  
-   [Application control](application-control.md)  
  
-   [Dispatch maps](dispatch-maps.md)  
  
 In addition, MFC provides a function called [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) that enables any OLE container developed with MFC 4.0 to fully support embedded OLE controls.  
  
## <a name="ole-controls"></a>OLE Controls  
  
-   [Variant parameter type constants](variant-parameter-type-constants.md)  
  
-   [Type library access](type-library-access.md)  
  
-   [Property pages](property-pages-mfc.md)  
  
-   [Event maps](event-maps.md)  
  
-   [Event sink maps](event-sink-maps.md)  
  
-   [Connection maps](connection-maps.md)  
  
-   [Registering OLE controls](registering-ole-controls.md)  
  
-   [Class factories and licensing](class-factories-and-licensing.md)  
  
-   [Persistence of OLE controls](persistence-of-ole-controls.md)  
  
 The first part of this section briefly discusses each of the previous categories and lists the globals and macros in the category, together with brief descriptions of functionality. Following this are descriptions of the global functions, global variables, and macros in the MFC library.  
  
> [!NOTE]
>  Many global functions start with the prefix "Afx", but some, for example, the dialog data exchange (DDX) functions and many of the database functions, do not follow this convention. All global variables start with "afx" as a prefix. Macros do not start with any particular prefix, but they are written in uppercase letters.  
  
## <a name="see-also"></a>See Also  
 [Class Overview](../../mfc/class-library-overview.md)




