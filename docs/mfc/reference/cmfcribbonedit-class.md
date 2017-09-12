---
title: CMFCRibbonEdit Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
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
ms.openlocfilehash: 29bb4a52a17779f4e62a9b528a6d86a78ca3ecef
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit Class
Implements an edit control that is located on a ribbon bar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Constructs a `CMFCRibbonEdit` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Indicates whether the height of the `CMFCRibbonEdit` control can increase vertically to the height of a ribbon row.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Constructs a `CMFCRibbonEdit` object.|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Copies the state of the specified `CMFCRibbonEdit` object to the current `CMFCRibbonEdit` object.|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|Creates a new text box for the `CMFCRibbonEdit` object.|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Destroys the `CMFCRibbonEdit` object.|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Drops down a list box.|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Enables and sets the range of the spin button for the text box.|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Retrieves the compact size of the `CFMCRibbonEdit` object.|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|Retrieves the text in the text box.|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Retrieves the intermediate size of the `CMFCRibbonEdit` object.|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Retrieves the alignment of the text in the text box.|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|Retrieves the width, in pixels, of the `CMFCRibbonEdit` control.|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Indicates whether the display size for the `CMFCRibbonEdit` control can be compact.|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Indicates whether the `CMFCRIbbonEdit` control has the focus.|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Indicates whether the display size for the `CMFCRibbonEdit` control can be large.|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Indicates whether the text box has a spin button.|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Indicates whether the `CMFCRibbonEdit` control is highlighted.|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Called by the framework when the dimensions of the display rectangle for the `CMFCRibbonEdit` control changes.|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|Called by the framework to draw the `CMFCRibbonEdit` control.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|Called by the framework to draw the label and image for the `CMFCRibbonEdit` control.|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Called by the framework to draw the `CMFCRibbonEdit` control in a commands list box.|  
|[CMFCRibbonEdit::OnEnable](#onenable)|Called by the framework to enable or disable the `CMFCRibbonEdit` control.|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|Called by the framework when the pointer enters or leaves the bounds of the `CMFCRibbonEdit` control.|  
|[CMFCRibbonEdit::OnKey](#onkey)|Called by the framework when the user presses a keytip and the `CMFCRibbonEdit` control has the focus.|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Called by the framework to update the `CMFCRibbonEdit` control when the user presses the left mouse button on the control.|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Called by the framework when the user releases the left mouse button.|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Called by the framework to update the `CMFCRibbonEdit` control when the layout changes direction.|  
|[CMFCRibbonEdit::OnShow](#onshow)|Called by the framework to show or hide the `CMFCRibbonEdit` control.|  
|[CMFCRibbonEdit::Redraw](#redraw)|Updates the display of the `CMFCRibbonEdit` control.|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Sets the accessibility data for the `CMFCRibbonEdit` object.|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|Sets the text in the text box.|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Sets the text alignment of the text box.|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|Sets the width of the text box for the `CMFCRibbonEdit` control.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="example"></a>Example  
 The following example demonstrates how to construct a `CMFCRibbonEdit` object, show spin buttons next to the edit control, and set the text of the edit control. This code snippet is part of the [MS Office 2007 Demo sample](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched  
 Indicates whether the height of the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control can increase vertically to the height of a ribbon row.  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>Return Value  
 Always returns `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit  
 Constructs a [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object.  
  
```  
CMFCRibbonEdit(
    UINT nID,  
    int nWidth,  
    LPCTSTR lpszLabel = NULL,  
    int nImage = -1);

CMFCRibbonEdit();
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nID`  
 Command ID for the `CMFCRibbonEdit` control.  
  
 [in] `nWidth`  
 The width, in pixels, of the text box for the `CMFCRibbonEdit` control.  
  
 [in] `lpszLabel`  
 The label for the `CMFCRibbonEdit` control.  
  
 [in] `nImage`  
 Index of the small image to use for the `CMFCRibbonEdit` control. The collection of small images is maintained by the parent ribbon category.  
  
### <a name="remarks"></a>Remarks  
 The `CMFCRibbonEdit` control does not use a large image.  
  
##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom  
 Copies the state of the specified [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object to the current [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `src`  
 The source `CMFCRibbonEdit` object.  
  
### <a name="remarks"></a>Remarks  
 The `src` parameter must be of type `CMFCRibbonEdit`.  
  
##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit  
 Creates a new text box for the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object.  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pWndParent`  
 A pointer to the parent window of the `CMFCRibbonEdit` object.  
  
 [in] `dwEditStyle`  
 Specifies the style of the text box. You can combine the window styles listed in the Remarks section with the [edit control styles](http://msdn.microsoft.com/library/windows/desktop/bb775464) that are described in the Windows SDK.  
  
### <a name="return-value"></a>Return Value  
 A pointer to the new text box if the method was successful; otherwise, `NULL`.  
  
### <a name="remarks"></a>Remarks  
 Override this method in a derived class to create a custom text box.  
  
 You can apply the following [Window Styles](../../mfc/reference/styles-used-by-mfc.md#window-styles) to a text box:  
  
- **WS_CHILD**  
  
- **WS_VISIBLE**  
  
- **WS_DISABLED**  
  
- **WS_GROUP**  
  
- **WS_TABSTOP**  
  
##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl  
 Destroys the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object.  
  
```  
virtual void DestroyCtrl();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList  
 Drops down a list box.  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>Remarks  
 By default this method does nothing. Override this method to drop down a list box.  
  
##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons  
 Enables and sets the range of the spin button for the text box.  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nMin`  
 The minimum value of the spin button.  
  
 [in] `nMax`  
 The maximum value of the spin button.  
  
### <a name="remarks"></a>Remarks  
 Spin buttons display an up and down arrow and enable users to move through a fixed set of values.  
  
##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize  
 Retrieves the compact size of the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object.  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to a device context for the `CMFCRibbonEdit` object.  
  
### <a name="return-value"></a>Return Value  
 The compact size of the `CMFCRibbonEdit` object.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText  
 Retrieves the text in the text box.  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The text in the text box.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize  
 Retrieves the intermediate size of the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to a device context for the `CMFCRibbonEdit` object.  
  
### <a name="return-value"></a>Return Value  
 The intermediate size of the `CMFCRibbonEdit` object.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign  
 Retrieves the alignment of the text in the text box.  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>Return Value  
 A text alignment enumerated value. See the Remarks section for possible values.  
  
### <a name="remarks"></a>Remarks  
 The returned value is one of the following edit control styles:  
  
- **ES_LEFT** for left alignment  
  
- **ES_CENTER** for center alignment  
  
- **ES_RIGHT** for right alignment  
  
 For more information about these styles, see [Edit Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth  
 Retrieves the width, in pixels, of the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bInFloatyMode`  
 `TRUE` if the `CMFCRibbonEdit` control is in floating mode; otherwise, `FALSE`.  
  
### <a name="return-value"></a>Return Value  
 The width, in pixels, of the `CMFCRibbonEdit` control.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode  
 Indicates whether the display size for the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control can be compact.  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Always returns `TRUE`.  
  
### <a name="remarks"></a>Remarks  
 By default this method always returns `TRUE`. Override this method to indicate whether the display size can be compact.  
  
##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus  
 Indicates whether the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control has the focus.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the `CMFCRibbonEdit` control has the focus; otherwise `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode  
 Indicates whether the display size for the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control can be large.  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Always returns `FALSE`.  
  
### <a name="remarks"></a>Remarks  
 By default this method always returns `FALSE`. Override this method to indicate whether the display size can be large.  
  
##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons  
 Indicates whether the text box has a spin button.  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the text box has a spin button; otherwise `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted  
 Indicates whether the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control is highlighted.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the `CMFCRibbonEdit` control is highlighted; otherwise `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect  
 Called by the framework when the dimensions of the display rectangle for the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control change.  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to a device context for the `CMFCRibbonEdit` control.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw  
 Called by the framework to draw the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to a device context for the `CMFCRibbonEdit` control.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage  
 Called by the framework to draw the label and image for the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to a device context for the `CMFCRibbonEdit` control.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList  
 Called by the framework to draw the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control in a commands list box.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pDC`  
 Pointer to a device context for the `CMFCRibbonEdit` control.  
  
 [in] `strText`  
 The display text [](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit class").  
  
 [in] `nTextOffset`  
 Distance, in pixels, from the left side of the list box to the display text.  
  
 [in] `rect`  
 The display rectangle for the `CMFCRibbonEdit` control.  
  
 [in] `bIsSelected`  
 This parameter is not used.  
  
 [in] `bHighlighted`  
 This parameter is not used.  
  
### <a name="remarks"></a>Remarks  
 The commands list box displays ribbon controls to enable users to customize the quick access toolbar.  
  
##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable  
 Called by the framework to enable or disable the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bEnable`  
 `TRUE` to enable the control; `FALSE` to disable the control.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight  
 Called by the framework when the pointer enters or leaves the bounds of the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bHighlight`  
 `TRUE` if the pointer is in the bounds of the `CMFCRibbonEdit` control; otherwise, `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey  
 Called by the framework when the user presses a keytip and the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control has the focus.  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bIsMenuKey`  
 `TRUE` if the keytip displays a pop-up menu; otherwise, `FALSE`.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the event was handled; otherwise, `FALSE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown  
 Called by the framework to update the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control when the user presses the left mouse button on the control.  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `point`  
 This parameter is not used.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp  
 Called by the framework when the user releases the left mouse button.  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `point`  
 This parameter is not used.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged  
 Called by the framework to update the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control when the layout changes direction.  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bIsRTL`  
 `TRUE` if the layout is right-to-left; `FALSE` if the layout is left-to-right.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow  
 Called by the framework to show or hide the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `bShow`  
 `TRUE` to show the control; `FALSE` to hide the control.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw  
 Updates the display of the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>Remarks  
 This method redraws the display rectangle for the `CMFCRibbonEdit` object by indirectly calling [CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911) with the `RDW_INVALIDATE`, `RDW_ERASE`, and `RDW_UPDATENOW` flags set.  
  
##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData  
 Sets the accessibility data for the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) object.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameters  
 `pParent`  
 Pointer to the parent window for the `CMFCRibbonEdit` object.  
  
 `data`  
 The accessibility data for the `CMFCRibbonEdit` object.  
  
### <a name="return-value"></a>Return Value  
 Always returns `TRUE`.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText  
 Sets the text in the text box.  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `strText`  
 The text for the text box.  
  
##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign  
 Sets the text alignment of the text box.  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nAlign`  
 A text alignment enumerated value. See the Remarks section for possible values.  
  
### <a name="remarks"></a>Remarks  
 The parameter `nAlign` is one of the following edit control styles:  
  
- **ES_LEFT** for left alignment  
  
- **ES_CENTER** for center alignment  
  
- **ES_RIGHT** for right alignment  
  
 For more information about these styles, see [Edit Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb775464).  
  
##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth  
 Sets the width of the text box for the [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) control.  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `nWidth`  
 The width, in pixels, of the text box.  
  
 `bInFloatyMode`  
 `TRUE` to set the width for floating mode; `FALSE` to set the width for regular mode.  
  
### <a name="remarks"></a>Remarks  
 The `CMFCRibbonEdit` control has two widths depending on its display mode: floating mode and regular mode.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)
