---
title: COleChangeIconDialog Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
dev_langs:
- C++
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
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
ms.openlocfilehash: b6ca28776cee2190380b370a121b918308635e19
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="colechangeicondialog-class"></a>COleChangeIconDialog Class
Used for the OLE Change Icon dialog box.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|Constructs a `COleChangeIconDialog` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|Performs the change specified in the dialog box.|  
|[COleChangeIconDialog::DoModal](#domodal)|Displays the OLE 2 Change Icon dialog box.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|Gets a handle to the metafile associated with the iconic form of this item.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|A structure that controls the behavior of the dialog box.|  
  
## <a name="remarks"></a>Remarks  
 Create an object of class `COleChangeIconDialog` when you want to call this dialog box. After a `COleChangeIconDialog` object has been constructed, you can use the [m_ci](#m_ci) structure to initialize the values or states of controls in the dialog box. The `m_ci` structure is of type **OLEUICHANGEICON**. For more information about using this dialog class, see the [DoModal](#domodal) member function.  
  
 For more information, see the [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) structure in the Windows SDK.  
  
 For more information about OLE-specific dialog boxes, see the article [Dialog Boxes in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxodlgs.h  
  
##  <a name="colechangeicondialog"></a>  COleChangeIconDialog::COleChangeIconDialog  
 This function constructs only a `COleChangeIconDialog` object.  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `pItem`  
 Points to the item to be converted.  
  
 `dwFlags`  
 Creation flag, which contains any number of the following values combined using the bitwise-or operator:  
  
- **CIF_SELECTCURRENT** Specifies that the Current radio button will be selected initially when the dialog box is called. This is the default.  
  
- **CIF_SELECTDEFAULT** Specifies that the Default radio button will be selected initially when the dialog box is called.  
  
- **CIF_SELECTFROMFILE** Specifies that the From File radio button will be selected initially when the dialog box is called.  
  
- **CIF_SHOWHELP** Specifies that the Help button will be displayed when the dialog box is called.  
  
- **CIF_USEICONEXE** Specifies that the icon should be extracted from the executable specified in the **szIconExe** field of [m_ci](#m_ci) instead of retrieved from the type. This is useful for embedding or linking to non-OLE files.  
  
 `pParentWnd`  
 Points to the parent or owner window object (of type `CWnd`) to which the dialog object belongs. If it is **NULL**, the parent window of the dialog box will be set to the main application window.  
  
### <a name="remarks"></a>Remarks  
 To display the dialog box, call the [DoModal](#domodal) function.  
  
 For more information, see the [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) structure in the Windows SDK.  
  
##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon  
 Call this function to change the icon representing the item to the one selected in the dialog box after [DoModal](#domodal) returns **IDOK**.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameters  
 `pItem`  
 Points to the item whose icon is changing.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if change is successful; otherwise 0.  
  
##  <a name="domodal"></a>  COleChangeIconDialog::DoModal  
 Call this function to display the OLE Change Icon dialog box.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Return Value  
 Completion status for the dialog box. One of the following values:  
  
- **IDOK** if the dialog box was successfully displayed.  
  
- **IDCANCEL** if the user canceled the dialog box.  
  
- **IDABORT** if an error occurred. If **IDABORT** is returned, call the `COleDialog::GetLastError` member function to get more information about the type of error that occurred. For a listing of possible errors, see the [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) function in the Windows SDK.  
  
### <a name="remarks"></a>Remarks  
 If you want to initialize the various dialog box controls by setting members of the [m_ci](#m_ci) structure, you should do this before calling `DoModal`, but after the dialog object is constructed.  
  
 If `DoModal` returns **IDOK**, you can call other member functions to retrieve the settings or information that was input by the user into the dialog box.  
  
##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile  
 Call this function to get a handle to the metafile that contains the iconic aspect of the selected item.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The handle to the metafile containing the iconic aspect of the new icon, if the dialog box was dismissed by choosing **OK**; otherwise, the icon as it was before the dialog was displayed.  
  
##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci  
 Structure of type **OLEUICHANGEICON** used to control the behavior of the Change Icon dialog box.  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>Remarks  
 Members of this structure can be modified either directly or through member functions.  
  
 For more information, see the [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) structure in the Windows SDK.  
  
## <a name="see-also"></a>See Also  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)

