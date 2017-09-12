---
title: COleLinksDialog Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
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
ms.openlocfilehash: fa51351bf888268c1bddf0f4b1247216de9e2e4d
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="colelinksdialog-class"></a>COleLinksDialog Class
Used for the OLE Edit Links dialog box.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Constructs a `COleLinksDialog` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|Displays the OLE Edit Links dialog box.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|A structure of type **OLEUIEDITLINKS** that controls the behavior of the dialog box.|  
  
## <a name="remarks"></a>Remarks  
 Create an object of class `COleLinksDialog` when you want to call this dialog box. After a `COleLinksDialog` object has been constructed, you can use the [m_el](#m_el) structure to initialize the values or states of controls in the dialog box. The `m_el` structure is of type **OLEUIEDITLINKS**. For more information about using this dialog class, see the [DoModal](#domodal) member function.  
  
> [!NOTE]
>  Application Wizard-generated container code uses this class.  
  
 For more information, see the [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) structure in the Windows SDK.  
  
 For more information regarding OLE-specific dialog boxes, see the article [Dialog Boxes in OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxodlgs.h  
  
##  <a name="domodal"></a>  COleLinksDialog::DoModal  
 Displays the OLE Edit Links dialog box.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Return Value  
 Completion status for the dialog box. One of the following values:  
  
- **IDOK** if the dialog box was successfully displayed.  
  
- **IDCANCEL** if the user canceled the dialog box.  
  
- **IDABORT** if an error occurred. If **IDABORT** is returned, call the `COleDialog::GetLastError` member function to get more information about the type of error that occurred. For a listing of possible errors, see the [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) function in the Windows SDK.  
  
### <a name="remarks"></a>Remarks  
 If you want to initialize the various dialog box controls by setting members of the [m_el](#m_el) structure, you should do it before calling `DoModal`, but after the dialog object is constructed.  
  
##  <a name="colelinksdialog"></a>  COleLinksDialog::COleLinksDialog  
 Constructs a `COleLinksDialog` object.  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `pDoc`  
 Points to the OLE document that contains the links to be edited.  
  
 `pView`  
 Points to the current view on `pDoc`.  
  
 `dwFlags`  
 Creation flag, which contains either 0 or **ELF_SHOWHELP** to specify whether the Help button will be displayed when the dialog box is displayed.  
  
 `pParentWnd`  
 Points to the parent or owner window object (of type `CWnd`) to which the dialog object belongs. If it is **NULL**, the parent window of the dialog box is set to the main application window.  
  
### <a name="remarks"></a>Remarks  
 This function constructs only a `COleLinksDialog` object. To display the dialog box, call the [DoModal](#domodal) function.  
  
##  <a name="m_el"></a>  COleLinksDialog::m_el  
 Structure of type **OLEUIEDITLINKS** used to control the behavior of the Edit Links dialog box.  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Remarks  
 Members of this structure can be modified either directly or through member functions.  
  
 For more information, see the [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) structure in the Windows SDK.  
  
## <a name="see-also"></a>See Also  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)

