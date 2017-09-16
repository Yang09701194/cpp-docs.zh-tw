---
title: Delegate and Interface Map Macros (MFC) | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
caps.latest.revision: 1
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
ms.openlocfilehash: 481801757db191eabe10d1f199afad29222636f3
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---

|||  
|-|-|  
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Begins a delegate map.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Begins the definition of the interfaced map.|
|[CommandHandler Delegate](#commandhandler)|Registers callback methods with a command source.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Ends a delegate map.|
|[END_INTERFACE_MAP](#end_interface_map)|Ends the interface map in the implementation file. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Creates an entry in the delegate map.|
|[INTERFACE_PART](#interface_part)|Used between the `BEGIN_INTERFACE_MAP` macro and the `END_INTERFACE_MAP` macro for each interface your object will support.|
|[MAKE_DELEGATE](#make_delegate)|Attaches an event handler to a managed control.|


## <a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP
Begins a delegate map.  
   
### <a name="syntax"></a>Syntax    
```  
BEGIN_DELEGATE_MAP(  CLASS );  
```
### <a name="parameters"></a>Parameters  
 `CLASS`  
 The class in which the managed control is hosted.  
   
### <a name="remarks"></a>Remarks  
 This macro marks the beginning of a list of delegate entries, which compose a delegate map. For an example of how this macro is used, see [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Requirements  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>See Also  
 [How to: Sink Windows Forms Events from Native C++ Classes](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)
 
##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP
Begins the definition of the interfaced map when used in the implementation file.  
   
### <a name="syntax"></a>Syntax    
```
BEGIN_INTERFACE_MAP( theClass, baseClass )  
```
### <a name="parameters"></a>Parameters  
 `theClass`  
 The class in which the interface map is to be defined  
  
 `baseClass`  
 The class from which `theClass` derives from.  
   
### <a name="remarks"></a>Remarks  
 For each interface that is implemented, there is one or more `INTERFACE_PART` macro invocations. For each aggregate that the class uses, there is one **INTERFACE_AGGREGATE** macro invocation.  
  
 For more information on interface maps, see [Technical Note 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
 
##  <a name="commandhandler"></a>CommandHandler Delegate
Registers callback methods with a command source.  
   
### <a name="syntax"></a>Syntax    
```  
delegate void CommandHandler(  UINT^ cmdID  );  
```
### <a name="parameters"></a>Parameters  
 `cmdID`  
 The command ID.  
   
### <a name="remarks"></a>Remarks  
 This delegate registers callback methods with a command source. When you add a delegate to the command source object, the callback method becomes a handler for commands coming from the specified source.  
  
 For more information, see [How to: Add Command Routing to the Windows Forms Control](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 For more information on using Windows Forms, see [Using a Windows Form User Control in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxwinforms.h (defined in assembly atlmfc\lib\mfcmifc80.dll)  
   
### <a name="see-also"></a>See Also  
 [How to: Add Command Routing to the Windows Forms Control](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)
 
##  <a name="commanduihandler"></a>CommandUIHandler
Registers callback methods with a user interface update command message.  
   
### <a name="syntax"></a>Syntax    
```  
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);  
```
### <a name="parameters"></a>Parameters  
 `cmdID`  
 The command ID.  
  
 `cmdUI`  
 The command message ID.  
   
### <a name="remarks"></a>Remarks  
 This delegate registers callback methods with a user interface update command message. `CommandUIHandler` is similar to [CommandHandler](#commandhandler) except that this delegate is used with user interface object update commands. User interface update commands should be mapped one-to-one with message handler methods.  
  
 For more information on using Windows Forms, see [Using a Windows Form User Control in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxwinforms.h (defined in assembly atlmfc\lib\mfcmifc80.dll)  
   
### <a name="see-also"></a>See Also  
 [How to: Add Command Routing to the Windows Forms Control](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [CommandHandler](#commandhandler)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP
Ends a delegate map.  
   
### <a name="syntax"></a>Syntax    
```  
END_DELEGATE_MAP();  
```  
   
### <a name="remarks"></a>Remarks  
 This macro marks the end of a list of delegate entries, which compose a delegate map. For an example of how this macro is used, see [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Requirements  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>See Also  

 [How to: Sink Windows Forms Events from Native C++ Classes](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

 
##  <a name="end_interface_map"></a>END_INTERFACE_MAP
Ends the interface map in the implementation file.  
   
### <a name="syntax"></a>Syntax    
```
END_INTERFACE_MAP( )    
```  
   
### <a name="remarks"></a>Remarks  
 For more information about interface maps, see [Technical Note 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
   
### <a name="see-also"></a>See Also  
 [Macros and Globals](mfc-macros-and-globals.md)   
 [BEGIN_INTERFACE_MAP](#begin_interface_map)
 

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY
Creates an entry in the delegate map.  
   
### <a name="syntax"></a>Syntax    
```  
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);  
```
### <a name="parameters"></a>Parameters  
 `MEMBER`  
 The event handler method to be attached to the control.  
  
 `ARG0`  
 The first argument of the managed event handler method, such as **Object^**.  
  
 `ARG1`  
 The second argument of the managed event handler method, such as **EventArgs^**.  
   
### <a name="remarks"></a>Remarks  
 Each entry in the delegate map corresponds to a managed event handler delegate created by [MAKE_DELEGATE](#make_delegate).  
   
### <a name="example"></a>Example  
 The following code example shows how to use `EVENT_DELEGATE_ENTRY` to create an entry in the delegate map for the `OnClick` event handler; also see the code example in `MAKE_DELEGATE`. For more information, see [How to: Sink Windows Forms Events from Native C++ Classes](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
 ```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()

```  
   
### <a name="requirements"></a>Requirements  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>See Also  
 [MAKE_DELEGATE](#make_delegate)   
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)
 

##  <a name="interface_part"></a>INTERFACE_PART
Used between the `BEGIN_INTERFACE_MAP` macro and the `END_INTERFACE_MAP` macro for each interface your object will support.  
   
### <a name="syntax"></a>Syntax    
```
INTERFACE_PART( theClass, iid, localClass)  
```
### <a name="parameters"></a>Parameters  
 `theClass`  
 The name of the class that contains the interface map.    
 `iid`  
 The IID that is to be mapped to the embedded class.    
 *localClass*  
 The name of the local class.  
   
### <a name="remarks"></a>Remarks  
 It allows you to map an IID to a member of the class indicated by `theClass` and *localClass*.  
  
 For more information on interface maps, see [Technical Note 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Requirements  
 **Header:** afxwin.h  
   
 
##  <a name="make_delegate"></a>MAKE_DELEGATE
Attaches an event handler to a managed control.  
   
### <a name="syntax"></a>Syntax    
```  
MAKE_DELEGATE( DELEGATE,  MEMBER) ;  
```
### <a name="parameters"></a>Parameters  
 `DELEGATE`  
 The type of the managed event handler delegate, such as [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True).  
  
 `MEMBER`  
 The name of the event handler method to be attached to the control.  
   
### <a name="remarks"></a>Remarks  
 This macro creates a managed event handler delegate of type `DELEGATE` and of the name `MEMBER`. The managed event handler delegate allows a native class to handle managed events.  
   
### <a name="example"></a>Example  
 The following code example shows how to call `MAKE_DELEGATE` to attach an `OnClick` event handler to an MFC control `MyControl`. For a broader explanation of how this macro works in an MFC application, see [How to: Sink Windows Forms Events from Native C++ Classes](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```
   
### <a name="requirements"></a>Requirements  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>See Also  
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)
 




