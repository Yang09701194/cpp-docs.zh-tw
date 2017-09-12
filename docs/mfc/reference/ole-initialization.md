---
title: OLE Initialization | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
caps.latest.revision: 13
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
ms.openlocfilehash: 5e756feff21f498129b0a077309b7784fd810212
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="ole-initialization"></a>OLE Initialization
Before an application can use OLE system services, it must initialize the OLE system DLLs and verify that the DLLs are the correct version. The **AfxOleInit** function initializes the OLE system DLLs.  
  
### <a name="ole-initialization"></a>OLE Initialization  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|Initializes the OLE libraries.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Call this function in your application object's `InitInstance` function to enable support for containment of OLE controls.| 


## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer
Call this function in your application object's `InitInstance` function to enable support for containment of OLE controls.  
   
### <a name="syntax"></a>Syntax    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>Remarks  
 For more information about OLE controls (now called ActiveX controls), see [ActiveX Control Topics](../mfc-activex-controls.md).  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxdisp.h  

  
##  <a name="afxoleinit"></a>  AfxOleInit  
 Initializes OLE support for the application.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; 0 if initialization fails, possibly because incorrect versions of the OLE system DLLs are installed.  
  
### <a name="remarks"></a>Remarks  
 Call this function to initialize the OLE support for an MFC application. When this function is called, the following actions occur:  
  
-   Initializes the COM library on the current apartment of the calling application. For more information, see [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Creates a message filter object, implementing the [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) interface. This message filter can be accessed with a call to [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
> [!NOTE]
>  If **AfxOleInit** is called from an MFC DLL, the call will fail. The failure occurs because the function assumes that, if it is called from a DLL, the OLE system was previously initialized by the calling application.  
  
> [!NOTE]
>  MFC applications must be initialized as single threaded apartment (STA). If you call [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in your `InitInstance` override, specify `COINIT_APARTMENTTHREADED` (rather than `COINIT_MULTITHREADED`). For more information, see PRB: MFC Application Stops Responding When You Initialize the Application as a Multithreaded Apartment (828643) at [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Requirements  
 **Header:** afxdisp.h

## <a name="see-also"></a>See Also  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

