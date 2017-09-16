---
title: COleChangeSourceDialog Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs:
- C++
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
caps.latest.revision: 22
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
ms.openlocfilehash: c019c02f677abeb9644bb83bf56d21dcf27e2605
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog Class
Used for the OLE Change Source dialog box.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|Constructs a `COleChangeSourceDialog` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|Displays the OLE Change Source dialog box.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|Gets the complete source display name.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|Gets the filename from the source name.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|Gets the prefix of the previous source.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|Gets the item name from the source name.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|Gets the prefix of the new source|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|Indicates if the source is valid.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|A structure that controls the behavior of the dialog box.|  
  
## <a name="remarks"></a>Remarks  
 Create an object of class `COleChangeSourceDialog` when you want to call this dialog box. After a `COleChangeSourceDialog` object has been constructed, you can use the [m_cs](#m_cs) structure to initialize the values or states of controls in the dialog box. The `m_cs` structure is of type [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160). For more information about using this dialog class, see the [DoModal](#domodal) member function.  
  
 For more information, see the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure in Windows SDK.  
  
 For more information about OLE-specific dialog boxes, see the article [Dialog Boxes in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog  
 This function constructs a `COleChangeSourceDialog` object.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `pItem`  
 Pointer to the linked [COleClientItem](../../mfc/reference/coleclientitem-class.md) whose source is to be updated.  
  
 `pParentWnd`  
 Points to the parent or owner window object (of type `CWnd`) to which the dialog object belongs. If it is **NULL**, the parent window of the dialog box will be set to the main application window.  
  
### <a name="remarks"></a>Remarks  
 To display the dialog box, call the [DoModal](#domodal) function.  
  
 For more information, see the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure and [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) function in Windows SDK.  
  
##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal  
 Call this function to display the OLE Change Source dialog box.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Return Value  
 Completion status for the dialog box. One of the following values:  
  
- **IDOK** if the dialog box was successfully displayed.  
  
- **IDCANCEL** if the user canceled the dialog box.  
  
- **IDABORT** if an error occurred. If **IDABORT** is returned, call the [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) member function to get more information about the type of error that occurred. For a listing of possible errors, see the [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) function in Windows SDK.  
  
### <a name="remarks"></a>Remarks  
 If you want to initialize the various dialog box controls by setting members of the [m_cs](#m_cs) structure, you should do this before calling `DoModal`, but after the dialog object is constructed.  
  
 If `DoModal` returns **IDOK**, you can call member functions to retrieve user-entered settings or information from the dialog box. The following list names typical query functions:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName  
 Call this function to retrieve the complete display name for the linked client item.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>Return Value  
 The complete source display name (moniker) for the [COleClientItem](../../mfc/reference/coleclientitem-class.md) specified in the constructor.  
  
##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName  
 Call this function to retrieve the file moniker portion of the display name for the linked client item.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>Return Value  
 The file moniker portion of the source display name for the [COleClientItem](../../mfc/reference/coleclientitem-class.md) specified in the constructor.  
  
### <a name="remarks"></a>Remarks  
 The file moniker together with the item moniker gives the complete display name.  
  
##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix  
 Call this function to get the previous prefix string for the source.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>Return Value  
 The previous prefix string of the source.  
  
### <a name="remarks"></a>Remarks  
 Call this function only after [DoModal](#domodal) returns **IDOK**.  
  
 This value comes directly from the **lpszFrom** member of the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure.  
  
 For more information, see the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure in Windows SDK.  
  
##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName  
 Call this function to retrieve the item moniker portion of the display name for the linked client item.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>Return Value  
 The item moniker portion of the source display name for the [COleClientItem](../../mfc/reference/coleclientitem-class.md) specified in the constructor.  
  
### <a name="remarks"></a>Remarks  
 The file moniker together with the item moniker gives the complete display name.  
  
##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix  
 Call this function to get the new prefix string for the source.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>Return Value  
 The new prefix string of the source.  
  
### <a name="remarks"></a>Remarks  
 Call this function only after [DoModal](#domodal) returns **IDOK**.  
  
 This value comes directly from the **lpszTo** member of the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure.  
  
 For more information, see the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure in Windows SDK.  
  
##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs  
 This data member is a structure of type [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>Remarks  
 `OLEUICHANGESOURCE` is used to control the behavior of the OLE Change Source dialog box. Members of this structure can be modified directly.  
  
 For more information, see the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure in Windows SDK.  
  
##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource  
 Call this function to determine if the new source is valid.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the new source is valid, otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 Call this function only after [DoModal](#domodal) returns **IDOK**.  
  
 For more information, see the [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) structure in Windows SDK.  
  
## <a name="see-also"></a>See Also  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)

