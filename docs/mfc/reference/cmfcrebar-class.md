---
title: CMFCReBar Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
dev_langs:
- C++
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
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
ms.openlocfilehash: 4531d69753b966a228363f9654cca893ec8766df
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcrebar-class"></a>CMFCReBar Class
A `CMFCReBar` object is a control bar that provides layout, persistence, and state information for rebar controls.  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCReBar : public CPane  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCReBar::AddBar](#addbar)|Adds a band to a rebar.|  
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Overrides [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCReBar::CanFloat](#canfloat)|(Overrides [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CMFCReBar::Create](#create)|Creates the rebar control and attaches it to the `CMFCReBar` object.|  
|[CMFCReBar::EnableDocking](#enabledocking)|(Overrides [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|  
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||  
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Provides direct access to the underlying [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) common control.|  
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Overrides [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Overrides [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|  
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Overrides [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/e139f06a-9793-4ee2-bc3d-517389368c77).)|  
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Overrides [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|  
  
## <a name="remarks"></a>Remarks  
 A `CMFCReBar` object can contain a variety of child windows. This includes edit boxes, toolbars, and list boxes. You can resize the rebar programmatically, or the user can manually resize the rebar by dragging its gripper bar. You can also set the background of a rebar object to a bitmap of your choice.  
  
 A rebar object behaves similarly to a toolbar object. A rebar control can contain one or more bands, and each band can contain a gripper bar, a bitmap, a text label, and a child window.  
  
## <a name="example"></a>Example  
 The following example demonstrates how to use various methods in the `CMFCReBar` class. The example shows how to create a rebar control and add a band to it. The band functions as an internal toolbar. This code snippet is part of the [Rebar Test sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxRebar.h  
  
##  <a name="addbar"></a>  CMFCReBar::AddBar  
 Adds a band to a rebar.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Parameters  
 [in] [out] `pBar`  
 A pointer to the child window that is to be inserted into the rebar. The referenced object must have the **WS_CHILD** window style.  
  
 [in] `pszText`  
 Specifies the text to appear on the rebar. The text is not part of the child window. Rather, it is displayed on the rebar itself.  
  
 [in] [out] `pbmp`  
 Specifies the bitmap to be displayed on the rebar background.  
  
 [in] `dwStyle`  
 Contains the style to apply to the band. For a complete list of band styles, see the description for `fStyle` in the [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) structure in the Windows SDK documentation.  
  
 [in] `clrFore`  
 Represents the foreground color of the rebar.  
  
 [in] `clrBack`  
 Represents the background color of the rebar.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the band was successfully added to the rebar; otherwise, `FALSE`.  
  
##  <a name="create"></a>  CMFCReBar::Create  
 Creates the rebar control and attaches it to the [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) object.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Parameters  
 [in] [out] `pParentWnd`  
 A pointer to the parent window of this rebar control.  
  
 [in] `dwCtrlStyle`  
 Specifies the style for the rebar control. The default style value is **RBS_BANDBORDERS**, which displays narrow lines to separate adjacent bands on the rebar control. For a list of valid styles, see [Rebar Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb774377) in the Windows SDK documentation.  
  
 [in] `dwStyle`  
 The window style of the rebar control. For a list of valid styles, see [Window Styles](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `nID`  
 The rebar's child-window ID.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the rebar was created successfully; otherwise, `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl  
 Provides direct access to `CReBarCtrl` the underlying common control for `CMFCReBar` objects.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A reference to the underlying `CReBarCtrl` object.  
  
### <a name="remarks"></a>Remarks  
 Call this method to take advantage of the Windows rebar common control functionality when customizing your rebar.  
  
##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="canfloat"></a>  CMFCReBar::CanFloat  

  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking  

  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `dwDockStyle`  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize  

  
```  
UINT GetReBarBandInfoSize() const;  
```  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `CPoint`  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Parameters  
 [in] `point`  
 [in] `pTI`  
  
### <a name="return-value"></a>Return Value  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment  

  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `dwAlignment`  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl Class](../../mfc/reference/crebarctrl-class.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)

