---
title: Application Control | Microsoft Docs
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
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
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
ms.openlocfilehash: 6022078118092b17b38a014eace7736328c6af83
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="application-control"></a>Application Control
OLE requires substantial control over applications and their objects. The OLE system DLLs must be able to launch and release applications automatically, coordinate their production and modification of objects, and so on. The functions in this topic meet those requirements. In addition to being called by the OLE system DLLs, these functions must sometimes be called by applications as well. 
  
### <a name="application-control"></a>Application Control  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Indicates whether the application can terminate.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Retrieves the application's current message filter.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Retrieves the current user-control flag.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Sets or clears the user-control flag.|  
|[AfxOleLockApp](#afxolelockapp)|Increments the framework's global count of the number of active objects in an application.|  
|[AfxOleLockControl](#afxolelockcontrol)| Locks the class factory of the specified control. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Decrements the framework's count of the number of active objects in an application.| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Unlocks the class factory of the specified control. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Registers a server in the OLE system registry.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Implements the user interface for the *typename* Object command.|  

  
##  <a name="afxolecanexitapp"></a>  AfxOleCanExitApp  
 Indicates whether the application can terminate.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the application can exit; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 An application should not terminate if there are outstanding references to its objects. The global functions `AfxOleLockApp` and `AfxOleUnlockApp` increment and decrement, respectively, a counter of references to the application's objects. The application should not terminate when this counter is nonzero. If the counter is nonzero, the application's main window is hidden (not destroyed) when the user chooses Close from the system menu or Exit from the File menu. The framework calls this function in **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Requirements  
 **Header**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>  AfxOleGetMessageFilter  
 Retrieves the application's current message filter.  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to the current message filter.  
  
### <a name="remarks"></a>Remarks  
 Call this function to access the current `COleMessageFilter`-derived object, just as you would call `AfxGetApp` to access the current application object.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Requirements  
 **Header**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>  AfxOleGetUserCtrl  
 Retrieves the current user-control flag.  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the user is in control of the application; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 The user is in control of the application when the user has explicitly opened or created a new document. The user is also in control if the application was not launched by the OLE system DLLs — in other words, if the user launched the application with the system shell.  

### <a name="requirements"></a>Requirements  
 **Header**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>  AfxOleSetUserCtrl  
 Sets or clears the user-control flag, which is explained in the reference for `AfxOleGetUserCtrl`.  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Parameters  
 *bUserCtrl*  
 Specifies whether the user-control flag is to be set or cleared.  
  
### <a name="remarks"></a>Remarks  
 The framework calls this function when the user creates or loads a document, but not when a document is loaded or created through an indirect action such as loading an embedded object from a container application.  
  
 Call this function if other actions in your application should put the user in control of the application.  

### <a name="requirements"></a>Requirements  
 **Header**: afxdisp.h

##  <a name="afxolelockapp"></a>  AfxOleLockApp  
 Increments the framework's global count of the number of active objects in the application.  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Remarks  
 The framework keeps a count of the number of objects active in an application. The `AfxOleLockApp` and `AfxOleUnlockApp` functions, respectively, increment and decrement this count.  
  
 When the user attempts to close an application that has active objects — an application for which the count of active objects is nonzero — the framework hides the application from the user's view instead of completely shutting it down. The `AfxOleCanExitApp` function indicates whether the application can terminate.  
  
 Call `AfxOleLockApp` from any object that exposes OLE interfaces, if it would be undesirable for that object to be destroyed while still being used by a client application. Also call `AfxOleUnlockApp` in the destructor of any object that calls `AfxOleLockApp` in the constructor. By default, `COleDocument` (and derived classes) automatically lock and unlock the application.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Requirements  
 **Header**: afxdisp.h

##  <a name="afxoleunlockapp"></a>  AfxOleUnlockApp  
 Decrements the framework's count of active objects in the application.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Remarks  
 See `AfxOleLockApp` for further information.  
  
 When the number of active objects reaches zero, **AfxOleOnReleaseAllObjects** is called.  
  
### <a name="example"></a>Example  
 See the example for [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Requirements  
 **Header**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
Locks the class factory of the specified control so that dynamically created data associated with the control remains in memory.  
   
### <a name="syntax"></a>Syntax    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parameters  
 `clsid`  
 The unique class ID of the control.  
  
 `lpszProgID`  
 The unique program ID of the control.  
   
### <a name="return-value"></a>Return Value  
 Nonzero if the class factory of the control was successfully locked; otherwise 0.  
   
### <a name="remarks"></a>Remarks  
 This can significantly speed up display of the controls. For example, once you create a control in a dialog box and lock the control with `AfxOleLockControl`, you do not need to create and kill it again every time the dialog is shown or destroyed. If the user opens and closes a dialog box repeatedly, locking your controls can significantly enhance performance. When you are ready to destroy the control, call `AfxOleUnlockControl`.  
   
### <a name="example"></a>Example  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>Requirements  
 **Header:** <afxwin.h>  
   
### <a name="see-also"></a>See Also  
 [Macros and Globals](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>  AfxOleRegisterServerClass  
 This function allows you to register your server in the OLE system registry.  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>Parameters  
 `clsid`  
 Reference to the server's OLE class ID.  
  
 `lpszClassName`  
 Pointer to a string containing the class name of the server's objects.  
  
 *lpszShortTypeName*  
 Pointer to a string containing the short name of the server's object type, such as "Chart."  
  
 *lpszLongTypeName*  
 Pointer to a string containing the long name of the server's object type, such as "Microsoft Excel 5.0 Chart."  
  
 `nAppType`  
 A value, taken from the **OLE_APPTYPE** enumeration, specifying the type of OLE application. Possible values are the following:  
  
- `OAT_INPLACE_SERVER` Server has full server user-interface.  
  
- `OAT_SERVER` Server supports only embedding.  
  
- `OAT_CONTAINER` Container supports links to embeddings.  
  
- `OAT_DISPATCH_OBJECT` `IDispatch`-capable object.  
  
 `rglpszRegister`  
 Array of pointers to strings representing the keys and values to be added to the OLE system registry if no existing values for the keys are found.  
  
 `rglpszOverwrite`  
 Array of pointers to strings representing the keys and values to be added to the OLE system registry if the registry contains existing values for the given keys.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the server class is successfully registered; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 Most applications can use **COleTemplateServer::Register** to register the application's document types. If your application's system-registry format does not fit the typical pattern, you can use `AfxOleRegisterServerClass` for more control.  
  
 The registry consists of a set of keys and values. The `rglpszRegister` and `rglpszOverwrite` arguments are arrays of pointers to strings, each consisting of a key and a value separated by a **NULL** character ( `'\0'`). Each of these strings can have replaceable parameters whose places are marked by the character sequences `%1` through `%5`.  
  
 The symbols are filled in as follows:  
  
|Symbol|Value|  
|------------|-----------|  
|%1|Class ID, formatted as a string|  
|%2|Class name|  
|%3|Path to executable file|  
|%4|Short type name|  
|%5|Long type name|  

### <a name="requirements"></a>Requirements  
 **Header**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>  AfxOleSetEditMenu  
 Implements the user interface for the *typename* Object command.  
  
```   
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>Parameters  
 `pClient`  
 A pointer to the client OLE item.  
  
 `pMenu`  
 A pointer to the menu object to be updated.  
  
 *iMenuItem*  
 The index of the menu item to be updated.  
  
 `nIDVerbMin`  
 The command ID that corresponds to the primary verb.  
  
 *nIDVerbMax*  
 The command ID that corresponds to the last verb.  
  
 *nIDConvert*  
 ID for the Convert menu item.  
  
### <a name="remarks"></a>Remarks  
 If the server recognizes only a primary verb, the menu item becomes "verb *typename* Object" and the `nIDVerbMin` command is sent when the user chooses the command. If the server recognizes several verbs, then the menu item becomes " *typename* Object" and a submenu listing all the verbs appears when the user chooses the command. When the user chooses a verb from the submenu, `nIDVerbMin` is sent if the first verb is chosen, `nIDVerbMin` + 1 is sent if the second verb is chosen, and so forth. The default `COleDocument` implementation automatically handles this feature.  
  
 You must have the following statement in your client's application resource script (.RC) file:  
  
 **#include \<afxolecl.rc>**  

### <a name="requirements"></a>Requirements  
 **Header**: afxole.h 

## <a name="see-also"></a>See Also  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a> AfxOleUnlockControl
Unlocks the class factory of the specified control.  
   
### <a name="syntax"></a>Syntax  
  ```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>Parameters  
 `clsid`  
 The unique class ID of the control.  
  
 `lpszProgID`  
 The unique program ID of the control.  
   
### <a name="return-value"></a>Return Value  
 Nonzero if the class factory of the control was successfully unlocked; otherwise 0.  
   
### <a name="remarks"></a>Remarks  
 A control is locked with `AfxOleLockControl`, so that dynamically created data associated with the control remains in memory. This can significantly speed up display of the control because the control need not be created and destroyed every time it is displayed. When you are ready to destroy the control, call `AfxOleUnlockControl`.  
   
### <a name="example"></a>Example  
 ```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>Requirements  
 **Header:** <afxwin.h>  
   
### <a name="see-also"></a>See Also  
 [Macros and Globals](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)


