---
title: CMFCRibbonMiniToolBar Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
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
ms.openlocfilehash: 60386835a2b309fd6672091202ed052061e27368
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar Class
Implements a contextual popup toolbar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Default constructor.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destructor.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Used by the framework to create a dynamic instance of this class type.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Used by the framework to obtain a pointer to the [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) object that is associated with this class type.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Overrides `CMFCPopupMenu::IsRibbonMiniToolBar`.)|  
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Sets the list of commands to be displayed on the toolbar.|  
|[CMFCRibbonMiniToolBar::Show](#show)|Displays the mini toolbar at the specified screen coordinates.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Displays the mini toolbar together with a context menu.|  
  
## <a name="remarks"></a>Remarks  
 The mini toolbar is typically displayed after the user selects an object in a document. For example, after the user selects a block of text in a word processing program, the application displays a mini toolbar that contains text formatting commands.  
  
 The mini toolbar becomes transparent when the mouse pointer is out of the bounds of the mini toolbar.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxRibbonMiniToolBar.h  
  
##  <a name="setcommands"></a>  CMFCRibbonMiniToolBar::SetCommands  
 Sets the list of commands to be displayed on the toolbar.  
  
```  
void SetCommands(
    CMFCRibbonBar* pRibbonBar,  
    const CList<UINT,UINT>& lstCommands);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pRibbonBar`  
 The ribbon bar that the mini toolbar searches for the buttons to display.  
  
 [in] `lstCommands`  
 The list of commands to be displayed on the mini toolbar. All ribbon categories are searched to find the associated buttons.  
  
### <a name="remarks"></a>Remarks  
 Use this function to set the list of commands to be displayed in the mini toolbar.  
  
### <a name="example"></a>Example  
 The following example demonstrates how to use the `SetCommands` method of the `CMFCRibbonMiniToolBar` class. This code snippet is part of the [MS Office 2007 Demo sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]  
  
##  <a name="show"></a>  CMFCRibbonMiniToolBar::Show  
 Displays the mini toolbar at the specified screen coordinates.  
  
```  
BOOL Show(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `x`  
 Specifies the horizontal position of the mini toolbar in screen coordinates.  
  
 [in] `y`  
 Specifies the vertical position of the mini toolbar in screen coordinates.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the mini toolbar was displayed successfully; otherwise, `FALSE`.  
  
##  <a name="showwithcontextmenu"></a>  CMFCRibbonMiniToolBar::ShowWithContextMenu  
 Displays the mini toolbar together with a context menu.  
  
```  
BOOL ShowWithContextMenu(
    int x,  
    int y,  
    UINT uiMenuResID,  
    CWnd* pWndOwner);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `x`  
 Specifies the horizontal position of the context menu in screen coordinates.  
  
 [in] `y`  
 Specifies the vertical position of the context menu in screen coordinates.  
  
 [in] `uiMenuResID`  
 Specifies the resource ID of the context menu to display.  
  
 [in] `pWndOwner`  
 Identifies the window which receives messages from the context menu.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the context menu was displayed successfully; otherwise, `FALSE`.  
  
### <a name="remarks"></a>Remarks  
 Use this function to display a mini toolbar that has a context menu. The context menu is positioned 15 pixels below the mini toolbar.  
  
##  <a name="iscontextmenumode"></a>  CMFCRibbonMiniToolBar::IsContextMenuMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsContextMenuMode() const;  
```  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isribbonminitoolbar"></a>  CMFCRibbonMiniToolBar::IsRibbonMiniToolBar  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsRibbonMiniToolBar() const;  
```  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

