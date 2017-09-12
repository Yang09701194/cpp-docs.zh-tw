---
title: CTabCtrl Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: 21
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
ms.openlocfilehash: 5714de6c675d433320ce3095205b4c78f9701323
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="ctabctrl-class"></a>CTabCtrl Class
Provides the functionality of the Windows common tab control.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|Constructs a `CTabCtrl` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|Calculates a tab control's display area given a window rectangle, or calculates the window rectangle that would correspond to a given display area.|  
|[CTabCtrl::Create](#create)|Creates a tab control and attaches it to an instance of a `CTabCtrl` object.|  
|[CTabCtrl::CreateEx](#createex)|Creates a tab control with the specified Windows extended styles and attaches it to an instance of a `CTabCtrl` object.|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Removes all items from a tab control.|  
|[CTabCtrl::DeleteItem](#deleteitem)|Removes an item from a tab control.|  
|[CTabCtrl::DeselectAll](#deselectall)|Resets items in a tab control, clearing any that were pressed.|  
|[CTabCtrl::DrawItem](#drawitem)|Draws a specified item of a tab control.|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|Retrieves the tab with the current focus of a tab control.|  
|[CTabCtrl::GetCurSel](#getcursel)|Determines the currently selected tab in a tab control.|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Retrieves the extended styles that are currently in use for the tab control.|  
|[CTabCtrl::GetImageList](#getimagelist)|Retrieves the image list associated with a tab control.|  
|[CTabCtrl::GetItem](#getitem)|Retrieves information about a tab in a tab control.|  
|[CTabCtrl::GetItemCount](#getitemcount)|Retrieves the number of tabs in the tab control.|  
|[CTabCtrl::GetItemRect](#getitemrect)|Retrieves the bounding rectangle for a tab in a tab control.|  
|[CTabCtrl::GetItemState](#getitemstate)|Retrieves the state of the indicated tab control item.|  
|[CTabCtrl::GetRowCount](#getrowcount)|Retrieves the current number of rows of tabs in a tab control.|  
|[CTabCtrl::GetToolTips](#gettooltips)|Retrieves the handle of the tool tip control associated with a tab control.|  
|[CTabCtrl::HighlightItem](#highlightitem)|Sets the highlight state of a tab item.|  
|[CTabCtrl::HitTest](#hittest)|Determines which tab, if any, is at a specified screen position.|  
|[CTabCtrl::InsertItem](#insertitem)|Inserts a new tab in a tab control.|  
|[CTabCtrl::RemoveImage](#removeimage)|Removes an image from a tab control's image list.|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|Sets the focus to a specified tab in a tab control.|  
|[CTabCtrl::SetCurSel](#setcursel)|Selects a tab in a tab control.|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Sets the extended styles for a tab control.|  
|[CTabCtrl::SetImageList](#setimagelist)|Assigns an image list to a tab control.|  
|[CTabCtrl::SetItem](#setitem)|Sets some or all of a tab's attributes.|  
|[CTabCtrl::SetItemExtra](#setitemextra)|Sets the number of bytes per tab reserved for application-defined data in a tab control.|  
|[CTabCtrl::SetItemSize](#setitemsize)|Sets the width and height of an item.|  
|[CTabCtrl::SetItemState](#setitemstate)|Sets the state of the indicated tab control item.|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Sets the minimum width of items in a tab control.|  
|[CTabCtrl::SetPadding](#setpadding)|Sets the amount of space (padding) around each tab's icon and label in a tab control.|  
|[CTabCtrl::SetToolTips](#settooltips)|Assigns a tool tip control to a tab control.|  
  
## <a name="remarks"></a>Remarks  
 A "tab control" is analogous to the dividers in a notebook or the labels in a file cabinet. By using a tab control, an application can define multiple pages for the same area of a window or dialog box. Each page consists of a set of information or a group of controls that the application displays when the user selects the corresponding tab. A special type of tab control displays tabs that look like buttons. Clicking a button should immediately perform a command instead of displaying a page.  
  
 This control (and therefore the `CTabCtrl` class) is available only to programs running under Windows 95/98 and Windows NT version 3.51 and later.  
  
 For more information on using `CTabCtrl`, see [Controls](../../mfc/controls-mfc.md) and [Using CTabCtrl](../../mfc/using-ctabctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxcmn.h  
  
##  <a name="adjustrect"></a>  CTabCtrl::AdjustRect  
 Calculates a tab control's display area given a window rectangle, or calculates the window rectangle that would correspond to a given display area.  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameters  
 `bLarger`  
 Indicates which operation to perform. If this parameter is **TRUE**, `lpRect` specifies a display rectangle and receives the corresponding window rectangle. If this parameter is **FALSE**, `lpRect` specifies a window rectangle and receives the corresponding display rectangle.  
  
 `lpRect`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure that specifies the given rectangle and receives the calculated rectangle.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="create"></a>  CTabCtrl::Create  
 Creates a tab control and attaches it to an instance of a `CTabCtrl` object.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Parameters  
 `dwStyle`  
 Specifies the tab control's style. Apply any combination of [tab control styles](http://msdn.microsoft.com/library/windows/desktop/bb760549), described in the Windows SDK. See **Remarks** for a list of window styles that you can also apply to the control.  
  
 `rect`  
 Specifies the tab control's size and position. It can be either a [CRect](../../atl-mfc-shared/reference/crect-class.md) object or a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure.  
  
 `pParentWnd`  
 Specifies the tab control's parent window, usually a `CDialog`. It must not be **NULL**.  
  
 `nID`  
 Specifies the tab control's ID.  
  
### <a name="return-value"></a>Return Value  
 **TRUE** if initialization of the object was successful; otherwise **FALSE**.  
  
### <a name="remarks"></a>Remarks  
 You construct a `CTabCtrl` object in two steps. First, call the constructor, and then call **Create**, which creates the tab control and attaches it to the `CTabCtrl` object.  
  
 In addition to tab control styles, you can apply the following window styles to a tab control:  
  
- **WS_CHILD** Creates a child window that represents the tab control. Cannot be used with the `WS_POPUP` style.  
  
- **WS_VISIBLE** Creates a tab control that is initially visible.  
  
- **WS_DISABLED** Creates a window that is initially disabled.  
  
- **WS_GROUP** Specifies the first control of a group of controls in which the user can move from one control to the next with the arrow keys. All controls defined with the **WS_GROUP** style after the first control belong to the same group. The next control with the **WS_GROUP** style ends the style group and starts the next group (that is, one group ends where the next begins).  
  
- **WS_TABSTOP** Specifies one of any number of controls through which the user can move by using the TAB key. The TAB key moves the user to the next control specified by the **WS_TABSTOP** style.  
  
 To create a tab control with extended window styles, call [CTabCtrl::CreateEx](#createex) instead of **Create**.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CTabCtrl::CreateEx  
 Creates a control (a child window) and associates it with the `CTabCtrl` object.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Parameters  
 `dwExStyle`  
 Specifies the extended style of the control being created. For a list of extended Windows styles, see the `dwExStyle` parameter for [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in the Windows SDK.  
  
 `dwStyle`  
 Specifies the tab control's style. Apply any combination of [tab control styles](http://msdn.microsoft.com/library/windows/desktop/bb760549), described in the Windows SDK. See **Remarks** in [Create](#create) for a list of window styles that you can also apply to the control.  
  
 `rect`  
 A reference to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure describing the size and position of the window to be created, in client coordinates of `pParentWnd`.  
  
 `pParentWnd`  
 A pointer to the window that is the control's parent.  
  
 `nID`  
 The control's child-window ID.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 Use `CreateEx` instead of [Create](#create) to apply extended Windows styles, specified by the Windows extended style preface **WS_EX_**.  
  
 `CreateEx` creates the control with the extended Windows styles specified by `dwExStyle`. Set extended styles specific to a control using [SetExtendedStyle](#setextendedstyle). For example, use `CreateEx` to set such styles as **WS_EX_CONTEXTHELP**, but use `SetExtendedStyle` to set such styles as **TCS_EX_FLATSEPARATORS**. For more information, see the styles described in [Tab Control Extended Styles](http://msdn.microsoft.com/library/windows/desktop/bb760546) in the Windows SDK.  
  
##  <a name="ctabctrl"></a>  CTabCtrl::CTabCtrl  
 Constructs a `CTabCtrl` object.  
  
```  
CTabCtrl();
```  
  
##  <a name="deleteallitems"></a>  CTabCtrl::DeleteAllItems  
 Removes all items from a tab control.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="deleteitem"></a>  CTabCtrl::DeleteItem  
 Removes the specified item from a tab control.  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 Zero-based value of the item to delete.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise 0.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="deselectall"></a>  CTabCtrl::DeselectAll  
 Resets items in a tab control, clearing any that were pressed.  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>Parameters  
 *fExcludeFocus*  
 Flag that specifies the scope of the item deselection. If this parameter is set to **FALSE**, all tab buttons will be reset. If it is set to **TRUE**, then all tab items except for the one currently selected will be reset.  
  
### <a name="remarks"></a>Remarks  
 This member function implements the behavior of the Win32 message, [TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579), as described in the Windows SDK.  
  
##  <a name="drawitem"></a>  CTabCtrl::DrawItem  
 Called by the framework when a visual aspect of an owner-draw tab control changes.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameters  
 `lpDrawItemStruct`  
 A pointer to a [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) structure describing the item to be painted.  
  
### <a name="remarks"></a>Remarks  
 The **itemAction** member of the `DRAWITEMSTRUCT` structure defines the drawing action that is to be performed.  
  
 By default, this member function does nothing. Override this member function to implement drawing for an owner-draw `CTabCtrl` object.  
  
 The application should restore all graphics device interface (GDI) objects selected for the display context supplied in `lpDrawItemStruct` before this member function terminates.  
  
##  <a name="getcurfocus"></a>  CTabCtrl::GetCurFocus  
 Retrieves the index of the tab with the current focus.  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The zero-based index of the tab with the current focus.  
  
##  <a name="getcursel"></a>  CTabCtrl::GetCurSel  
 Retrieves the currently selected tab in a tab control.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Zero-based index of the selected tab if successful or - 1 if no tab is selected.  
  
##  <a name="getextendedstyle"></a>  CTabCtrl::GetExtendedStyle  
 Retrieves the extended styles that are currently in use for the tab control.  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>Return Value  
 Represents the extended styles currently in use for the tab control. This value is a combination of [tab control extended styles](http://msdn.microsoft.com/library/windows/desktop/bb760546), as described in the Windows SDK.  
  
### <a name="remarks"></a>Remarks  
 This member function implements the behavior of the Win32 message [TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585), as described in the Windows SDK.  
  
##  <a name="getimagelist"></a>  CTabCtrl::GetImageList  
 Retrieves the image list that's associated with a tab control.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Return Value  
 If successful, a pointer to the image list of the tab control; otherwise, **NULL**.  
  
##  <a name="getitem"></a>  CTabCtrl::GetItem  
 Retrieves information about a tab in a tab control.  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 Zero-based index of the tab.  
  
 `pTabCtrlItem`  
 Pointer to a [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure, used to specify the information to retrieve. Also used to receive information about the tab. This structure is used with the `InsertItem`, `GetItem`, and `SetItem` member functions.  
  
### <a name="return-value"></a>Return Value  
 Returns **TRUE** if successful; **FALSE** otherwise.  
  
### <a name="remarks"></a>Remarks  
 When the message is sent, the **mask** member specifies which attributes to return. If the **mask** member specifies the `TCIF_TEXT` value, the **pszText** member must contain the address of the buffer that receives the item text and the **cchTextMax** member must specify the size of the buffer.  
  
 **mask**  
 Value specifying which `TCITEM` structure members to retrieve or set. This member can be zero or a combination of the following values:  
  
- `TCIF_TEXT` The **pszText** member is valid.  
  
- `TCIF_IMAGE` The `iImage` member is valid.  
  
- `TCIF_PARAM` The **lParam** member is valid.  
  
- `TCIF_RTLREADING` The text of **pszText** is displayed using right-to-left reading order on Hebrew or Arabic systems.  
  
- `TCIF_STATE` The **dwState** member is valid.  
  
 **pszText**  
 Pointer to a null-terminated string containing the tab text if the structure contains information about a tab. If the structure is receiving information, this member specifies the address of the buffer that receives the tab text.  
  
 **cchTextMax**  
 Size of the buffer pointed to by **pszText**. This member is ignored if the structure is not receiving information.  
  
 `iImage`  
 Index into the tab control's image list, or - 1 if there is no image for the tab.  
  
 **lParam**  
 Application-defined data associated with the tab. If there are more than four bytes of application-defined data per tab, an application must define a structure and use it instead of the `TCITEM` structure. The first member of the application-defined structure must be a [TCITEMHEADER](http://msdn.microsoft.com/library/windows/desktop/bb760556)structure. The **TCITEMHEADER** structure is identical to the `TCITEM` structure, but without the **lParam** member. The difference between the size of your structure and the size of the **TCITEMHEADER** structure should equal the number of extra bytes per tab.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="getitemcount"></a>  CTabCtrl::GetItemCount  
 Retrieves the number of tabs in the tab control.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Number of items in the tab control.  
  
### <a name="example"></a>Example  
  See the example for [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemrect"></a>  CTabCtrl::GetItemRect  
 Retrieves the bounding rectangle for the specified tab in a tab control.  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 Zero-based index of the tab item.  
  
 `lpRect`  
 Pointer to a [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure that receives the bounding rectangle of the tab. These coordinates use the viewport's current mapping mode.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise 0.  
  
### <a name="example"></a>Example  
  See the example for [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemstate"></a>  CTabCtrl::GetItemState  
 Retrieves the state of the tab control item identified by `nItem`.  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 The zero-based index number of the item for which to retrieve state information.  
  
 `dwMask`  
 Mask specifying which of the item's state flags to return. For a list of values, see the mask member of the [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure, as described in the Windows SDK.  
  
### <a name="return-value"></a>Return Value  
 A reference to a `DWORD` value receiving the state information. Can be one of the following values:  
  
|Value|Description|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|The tab control item is selected.|  
|**TCIS_HIGHLIGHTED**|The tab control item is highlighted, and the tab and text are drawn using the current highlight color. When using highlight color, this will be a true interpolation, not a dithered color.|  
  
### <a name="remarks"></a>Remarks  
 An item's state is specified by the **dwState** member of the `TCITEM` structure.  
  
##  <a name="getrowcount"></a>  CTabCtrl::GetRowCount  
 Retrieves the current number of rows in a tab control.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The number of rows of tabs in the tab control.  
  
### <a name="remarks"></a>Remarks  
 Only tab controls that have the **TCS_MULTILINE** style can have multiple rows of tabs.  
  
##  <a name="gettooltips"></a>  CTabCtrl::GetToolTips  
 Retrieves the handle of the tool tip control associated with a tab control.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Return Value  
 Handle of the tool tip control if successful; otherwise **NULL**.  
  
### <a name="remarks"></a>Remarks  
 A tab control creates a tool tip control if it has the **TCS_TOOLTIPS** style. You can also assign a tool tip control to a tab control by using the `SetToolTips` member function.  
  
##  <a name="highlightitem"></a>  CTabCtrl::HighlightItem  
 Sets the highlight state of a tab item.  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parameters  
 `idItem`  
 Zero-based index of a tab control item.  
  
 `fHighlight`  
 Value specifying the highlight state to be set. If this value is **TRUE**, the tab is highlighted; if **FALSE**, the tab is set to its default state.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise zero.  
  
### <a name="remarks"></a>Remarks  
 This member function implements the Win32 message [TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602), as described in the Windows SDK.  
  
##  <a name="hittest"></a>  CTabCtrl::HitTest  
 Determines which tab, if any, is at the specified screen position.  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `pHitTestInfo`  
 Pointer to a [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553) structure, as described in the Windows SDK, which specifies the screen position to test.  
  
### <a name="return-value"></a>Return Value  
 Returns the zero-based index of the tab or - 1 if no tab is at the specified position.  
  
##  <a name="insertitem"></a>  CTabCtrl::InsertItem  
 Inserts a new tab in an existing tab control.  
  
```  
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

 
LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

 
LONG InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage,  
    LPARAM lParam,  
    DWORD dwState,  
    DWORD dwStateMask);
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 Zero-based index of the new tab.  
  
 `pTabCtrlItem`  
 Pointer to a [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure that specifies the attributes of the tab.  
  
 `lpszItem`  
 Address of a null-terminated string that contains the text of the tab.  
  
 `nImage`  
 The zero-based index of an image to insert from an image list.  
  
 `nMask`  
 Specifies which `TCITEM` structure attributes to set. Can be zero or a combination of the following values:  
  
- `TCIF_TEXT` The **pszText** member is valid.  
  
- `TCIF_IMAGE` The `iImage` member is valid.  
  
- `TCIF_PARAM` The **lParam** member is valid.  
  
- `TCIF_RTLREADING` The text of **pszText** is displayed using right-to-left reading order on Hebrew or Arabic systems.  
  
- `TCIF_STATE` The **dwState** member is valid.  
  
 `lParam`  
 Application-defined data associated with the tab.  
  
 `dwState`  
 Specifies values for the item's states. For more information, see [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) in the Windows SDK.  
  
 *dwStateMask*  
 Specifies which states are to be set. For more information, see [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) in the Windows SDK.  
  
### <a name="return-value"></a>Return Value  
 Zero-based index of the new tab if successful; otherwise - 1.  
  
### <a name="example"></a>Example  
 [!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="removeimage"></a>  CTabCtrl::RemoveImage  
 Removes the specified image from a tab control's image list.  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>Parameters  
 `nImage`  
 Zero-based index of the image to remove.  
  
### <a name="remarks"></a>Remarks  
 The tab control updates each tab's image index so that each tab remains associated with the same image.  
  
##  <a name="setcurfocus"></a>  CTabCtrl::SetCurFocus  
 Sets the focus to a specified tab in a tab control.  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 Specifies the index of the tab that gets the focus.  
  
### <a name="remarks"></a>Remarks  
 This member function implements the behavior of the Win32 message [TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610), as described in the Windows SDK.  
  
##  <a name="setcursel"></a>  CTabCtrl::SetCurSel  
 Selects a tab in a tab control.  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 The zero-based index of the item to be selected.  
  
### <a name="return-value"></a>Return Value  
 Zero-based index of the previously selected tab if successful, otherwise - 1.  
  
### <a name="remarks"></a>Remarks  
 A tab control does not send a **TCN_SELCHANGING** or **TCN_SELCHANGE** notification message when a tab is selected using this function. These notifications are sent, using **WM_NOTIFY**, when the user clicks or uses the keyboard to change tabs.  
  
##  <a name="setextendedstyle"></a>  CTabCtrl::SetExtendedStyle  
 Sets the extended styles for a tab control.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>Parameters  
 `dwNewStyle`  
 Value specifying a combination of tab control extended styles.  
  
 `dwExMask`  
 A `DWORD` value that indicates which styles in `dwNewStyle` are to be affected. Only the extended styles in `dwExMask` will be changed. All other styles will be maintained as is. If this parameter is zero, then all of the styles in `dwNewStyle` will be affected.  
  
### <a name="return-value"></a>Return Value  
 A `DWORD` value that contains the previous [tab control extended styles](http://msdn.microsoft.com/library/windows/desktop/bb760546), as described in the Windows SDK.  
  
### <a name="return-value"></a>Return Value  
 This member function implements the behavior of the Win32 message [TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627), as described in the Windows SDK.  
  
##  <a name="setimagelist"></a>  CTabCtrl::SetImageList  
 Assigns an image list to a tab control.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameters  
 `pImageList`  
 Pointer to the image list to be assigned to the tab control.  
  
### <a name="return-value"></a>Return Value  
 Returns a pointer to the previous image list or **NULL** if there is no previous image list.  
  
##  <a name="setitem"></a>  CTabCtrl::SetItem  
 Sets some or all of a tab's attributes.  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 Zero-based index of the item.  
  
 `pTabCtrlItem`  
 Pointer to a [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure that contains the new item attributes. The **mask** member specifies which attributes to set. If the **mask** member specifies the `TCIF_TEXT` value, the **pszText** member is the address of a null-terminated string and the **cchTextMax** member is ignored.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise 0.  
  
### <a name="example"></a>Example  
  See the example for [GetItem](#getitem).  
  
##  <a name="setitemextra"></a>  CTabCtrl::SetItemExtra  
 Sets the number of bytes per tab reserved for application-defined data in a tab control.  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>Parameters  
 `nBytes`  
 The number of extra bytes to set.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise zero.  
  
### <a name="remarks"></a>Remarks  
 This member function implements the behavior of the Win32 message [TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633), as described in the Windows SDK.  
  
##  <a name="setitemsize"></a>  CTabCtrl::SetItemSize  
 Sets the width and height of the tab control items.  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>Parameters  
 `size`  
 The new width and height, in pixels, of the tab control items.  
  
### <a name="return-value"></a>Return Value  
 Returns the old width and height of the tab control items.  
  
##  <a name="setitemstate"></a>  CTabCtrl::SetItemState  
 Sets the state of the tab control item identified by `nItem`.  
  
```  
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 The zero-based index number of the item for which to set state information.  
  
 `dwMask`  
 Mask specifying which of the item's state flags to set. For a list of values, see the mask member of the [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) structure, as described in the Windows SDK.  
  
 `dwState`  
 A reference to a `DWORD` value containing the state information. Can be one of the following values:  
  
|Value|Description|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|The tab control item is selected.|  
|**TCIS_HIGHLIGHTED**|The tab control item is highlighted, and the tab and text are drawn using the current highlight color. When using highlight color, this will be a true interpolation, not a dithered color.|  
  
### <a name="return-value"></a>Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setmintabwidth"></a>  CTabCtrl::SetMinTabWidth  
 Sets the minimum width of items in a tab control.  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>Parameters  
 `cx`  
 Minimum width to be set for a tab control item. If this parameter is set to -1, the control will use the default tab width.  
  
### <a name="return-value"></a>Return Value  
 The previous minimum tab width.  
  
### <a name="return-value"></a>Return Value  
 This member function implements the behavior of the Win32 message [TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637), as described in the Windows SDK.  
  
##  <a name="setpadding"></a>  CTabCtrl::SetPadding  
 Sets the amount of space (padding) around each tab's icon and label in a tab control.  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>Parameters  
 `size`  
 Sets the amount of space (padding) around each tab's icon and label in a tab control.  
  
##  <a name="settooltips"></a>  CTabCtrl::SetToolTips  
 Assigns a tool tip control to a tab control.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parameters  
 `pWndTip`  
 Handle of the tool tip control.  
  
### <a name="remarks"></a>Remarks  
 You can get the tool tip control associated with a tab control by making a call to `GetToolTips`.  
  
### <a name="example"></a>Example  
  See the example for [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
## <a name="see-also"></a>See Also  
 [CWnd Class](../../mfc/reference/cwnd-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl Class](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)

