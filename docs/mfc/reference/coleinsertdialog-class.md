---
title: COleInsertDialog Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
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
ms.openlocfilehash: a890bca0062dd3089cf4a84f43150497262dd8f7
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="coleinsertdialog-class"></a>COleInsertDialog Class
Used for the OLE Insert Object dialog box.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Constructs a `COleInsertDialog` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](#createitem)|Creates the item selected in the dialog box.|  
|[COleInsertDialog::DoModal](#domodal)|Displays the OLE Insert Object dialog box.|  
|[COleInsertDialog::GetClassID](#getclassid)|Gets the **CLSID** associated with the chosen item.|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Tells whether to draw the item as an icon.|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Gets a handle to the metafile associated with the iconic form of this item.|  
|[COleInsertDialog::GetPathName](#getpathname)|Gets the full path to the file chosen in the dialog box.|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Gets the type of object selected.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|A structure of type **OLEUIINSERTOBJECT** that controls the behavior of the dialog box.|  
  
## <a name="remarks"></a>Remarks  
 Create an object of class `COleInsertDialog` when you want to call this dialog box. After a `COleInsertDialog` object has been constructed, you can use the [m_io](#m_io) structure to initialize the values or states of controls in the dialog box. The `m_io` structure is of type **OLEUIINSERTOBJECT**. For more information about using this dialog class, see the [DoModal](#domodal) member function.  
  
> [!NOTE]
>  Application Wizard-generated container code uses this class.  
  
 For more information, see the [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) structure in the Windows SDK.  
  
 For more information regarding OLE-specific dialog boxes, see the article [Dialog Boxes in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>  COleInsertDialog::COleInsertDialog  
 This function constructs only a `COleInsertDialog` object.  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `dwFlags`  
 Creation flag that contains any number of the following values to be combined using the bitwise-OR operator:  
  
- **IOF_SHOWHELP** Specifies that the Help button will be displayed when the dialog box is called.  
  
- **IOF_SELECTCREATENEW** Specifies that the Create New radio button will be selected initially when the dialog box is called. This is the default and cannot be used with **IOF_SELECTCREATEFROMFILE**.  
  
- **IOF_SELECTCREATEFROMFILE** Specifies that the Create From File radio button will be selected initially when the dialog box is called. Cannot be used with **IOF_SELECTCREATENEW**.  
  
- **IOF_CHECKLINK** Specifies that the Link check box will be checked initially when the dialog box is called.  
  
- **IOF_DISABLELINK** Specifies that the Link check box will be disabled when the dialog box is called.  
  
- **IOF_CHECKDISPLAYASICON** Specifies that the Display As Icon check box will be checked initially, the current icon will be displayed, and the Change Icon button will be enabled when the dialog box is called.  
  
- **IOF_VERIFYSERVERSEXIST** Specifies that the dialog box should validate the classes it adds to the list box by ensuring that the servers specified in the registration database exist before the dialog box is displayed. Setting this flag can significantly impair performance.  
  
 `pParentWnd`  
 Points to the parent or owner window object (of type `CWnd`) to which the dialog object belongs. If it is **NULL**, the parent window of the dialog object is set to the main application window.  
  
### <a name="remarks"></a>Remarks  
 To display the dialog box, call the [DoModal](#domodal) function.  
  
##  <a name="createitem"></a>  COleInsertDialog::CreateItem  
 Call this function to create an object of type [COleClientItem](../../mfc/reference/coleclientitem-class.md) only if [DoModal](#domodal) returns **IDOK**.  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Parameters  
 `pItem`  
 Points to the item to be created.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if item was created; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 You must allocate the `COleClientItem` object before you can call this function.  
  
##  <a name="domodal"></a>  COleInsertDialog::DoModal  
 Call this function to display the OLE Insert Object dialog box.  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>Parameters  
 `dwFlags`  
 One of the following values:  
  
 `COleInsertDialog::DocObjectsOnly` inserts only DocObjects.  
  
 `COleInsertDialog::ControlsOnly` inserts only ActiveX controls.  
  
 Zero inserts neither a DocObject nor an ActiveX control. This value results in the same implementation as the first prototype listed above.  
  
### <a name="return-value"></a>Return Value  
 Completion status for the dialog box. One of the following values:  
  
-   IDOK if the dialog box was successfully displayed.  
  
-   IDCANCEL if the user canceled the dialog box.  
  
-   IDABORT if an error occurred. If IDABORT is returned, call the [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) member function to get more information about the type of error that occurred. For a listing of possible errors, see the [OleUIInsertObject](http://msdn.microsoft.com/library/windows/desktop/ms694325) function in the Windows SDK.  
  
### <a name="remarks"></a>Remarks  
 If you want to initialize the various dialog box controls by setting members of the [m_io](#m_io) structure, you should do this before calling `DoModal`, but after the dialog object is constructed.  
  
 If `DoModal` returns IDOK, you can call other member functions to retrieve the settings or information input into the dialog box by the user.  
  
##  <a name="getclassid"></a>  COleInsertDialog::GetClassID  
 Call this function to get the **CLSID** associated with the selected item only if [DoModal](#domodal) returns **IDOK** and the selection type is **COleInsertDialog::createNewItem**.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Returns the **CLSID** associated with the selected item.  
  
### <a name="remarks"></a>Remarks  
 For more information, see [CLSID Key](http://msdn.microsoft.com/library/windows/desktop/ms691424) in the Windows SDK.  
  
##  <a name="getdrawaspect"></a>  COleInsertDialog::GetDrawAspect  
 Call this function to determine if the user chose to display the selected item as an icon.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The method needed to render the object.  
  
- `DVASPECT_CONTENT` Returned if the Display As Icon check box was not checked.  
  
- `DVASPECT_ICON` Returned if the Display As Icon check box was checked.  
  
### <a name="remarks"></a>Remarks  
 Call this function only if [DoModal](#domodal) returns **IDOK**.  
  
 For more information on drawing aspect, see [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) data structure in the Windows SDK.  
  
##  <a name="geticonicmetafile"></a>  COleInsertDialog::GetIconicMetafile  
 Call this function to get a handle to the metafile that contains the iconic aspect of the selected item.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The handle to the metafile containing the iconic aspect of the selected item, if the Display As Icon check box was checked when the dialog was dismissed by choosing **OK**; otherwise **NULL**.  
  
##  <a name="getpathname"></a>  COleInsertDialog::GetPathName  
 Call this function to get the full path of the selected file only if [DoModal](#domodal) returns **IDOK** and the selection type is not **COleInsertDialog::createNewItem**.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The full path to the file selected in the dialog box. If the selection type is `createNewItem`, this function returns a meaningless `CString` in release mode or causes an assertion in debug mode.  
  
##  <a name="getselectiontype"></a>  COleInsertDialog::GetSelectionType  
 Call this function to get the selection type chosen when the Insert Object dialog box was dismissed by choosing **OK**.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Type of selection made.  
  
### <a name="remarks"></a>Remarks  
 The return type values are specified by the **Selection** enumeration type declared in the `COleInsertDialog` class.  
  
```  
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };  
```  
  
 Brief descriptions of these values follow:  
  
- **COleInsertDialog::createNewItem** The Create New radio button was selected.  
  
- **COleInsertDialog::insertFromFile** The Create From File radio button was selected and the Link check box was not checked.  
  
- **COleInsertDialog::linkToFile** The Create From File radio button was selected and the Link check box was checked.  
  
##  <a name="m_io"></a>  COleInsertDialog::m_io  
 Structure of type **OLEUIINSERTOBJECT** used to control the behavior of the Insert Object dialog box.  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>Remarks  
 Members of this structure can be modified either directly or through member functions.  
  
 For more information, see the [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) structure in the Windows SDK.  
  
## <a name="see-also"></a>See Also  
 [MFC Sample OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)

