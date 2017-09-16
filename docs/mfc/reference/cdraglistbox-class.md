---
title: CDragListBox Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
dev_langs:
- C++
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
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
ms.openlocfilehash: 7867c4d7b3e242c7d59044b93fe9dee3caddc9dd
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cdraglistbox-class"></a>CDragListBox Class
In addition to providing the functionality of a Windows list box, the `CDragListBox` class allows the user to move list box items, such as filenames, within the list box.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|Constructs a `CDragListBox` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|Called by the framework when a drag operation starts.|  
|[CDragListBox::CancelDrag](#canceldrag)|Called by the framework when a drag operation has been canceled.|  
|[CDragListBox::Dragging](#dragging)|Called by the framework during a drag operation.|  
|[CDragListBox::DrawInsert](#drawinsert)|Draws the insertion guide of the drag list box.|  
|[CDragListBox::Dropped](#dropped)|Called by the framework after the item has been dropped.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|Returns the coordinates of the item being dragged.|  
  
## <a name="remarks"></a>Remarks  
 List boxes with this capability allow users to order the items in a list in whatever manner is most useful to them. By default, the list box will move the item to the new location in the list. However, `CDragListBox` objects can be customized to copy items instead of moving them.  
  
 The list box control associated with the `CDragListBox` class must not have the **LBS_SORT** or the **LBS_MULTIPLESELECT** style. For a description of list box styles, see [List-Box Styles](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).  
  
 To use a drag list box in an existing dialog box of your application, add a list box control to your dialog template using the dialog editor and then assign a member variable (of Category `Control` and Variable Type `CDragListBox`) corresponding to the list box control in your dialog template.  
  
 For more information on assigning controls to member variables, see [Shortcut for Defining Member Variables for Dialog Controls](../../windows/defining-member-variables-for-dialog-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxcmn.h  
  
##  <a name="begindrag"></a>  CDragListBox::BeginDrag  
 Called by the framework when an event occurs that could begin a drag operation, such as pressing the left mouse button.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parameters  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that contains the coordinates of the item being dragged.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if dragging is allowed, otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 Override this function if you want to control what happens when a drag operation begins. The default implementation captures the mouse and stays in drag mode until the user clicks the left or right mouse button or presses ESC, at which time the drag operation is canceled.  
  
##  <a name="canceldrag"></a>  CDragListBox::CancelDrag  
 Called by the framework when a drag operation has been canceled.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parameters  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that contains the coordinates of the item being dragged.  
  
### <a name="remarks"></a>Remarks  
 Override this function to handle any special processing for your list box control.  
  
##  <a name="cdraglistbox"></a>  CDragListBox::CDragListBox  
 Constructs a `CDragListBox` object.  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>  CDragListBox::Dragging  
 Called by the framework when a list box item is being dragged within the `CDragListBox` object.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>Parameters  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that contains the x and y screen coordinates of the cursor.  
  
### <a name="return-value"></a>Return Value  
 The resource ID of the cursor to be displayed. The following values are possible:  
  
- `DL_COPYCURSOR` Indicates that the item will be copied.  
  
- `DL_MOVECURSOR` Indicates that the item will be moved.  
  
- `DL_STOPCURSOR` Indicates that the current drop target is not acceptable.  
  
### <a name="remarks"></a>Remarks  
 The default behavior returns `DL_MOVECURSOR`. Override this function if you want to provide additional functionality.  
  
##  <a name="drawinsert"></a>  CDragListBox::DrawInsert  
 Called by the framework to draw the insertion guide before the item with the indicated index.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>Parameters  
 `nItem`  
 Zero-based index of the insertion point.  
  
### <a name="remarks"></a>Remarks  
 A value of - 1 clears the insertion guide. Override this function to modify the appearance or behavior of the insertion guide.  
  
##  <a name="dropped"></a>  CDragListBox::Dropped  
 Called by the framework when an item is dropped within a `CDragListBox` object.  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>Parameters  
 *nSrcIndex*  
 Specifies the zero-based index of the dropped string.  
  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object that contains the coordinates of the drop site.  
  
### <a name="remarks"></a>Remarks  
 The default behavior copies the list box item and its data to the new location and then deletes the original item. Override this function to customize the default behavior, such as enabling copies of list box items to be dragged to other locations within the list.  
  
##  <a name="itemfrompt"></a>  CDragListBox::ItemFromPt  
 Call this function to retrieve the zero-based index of the list box item located at `pt`.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameters  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) object containing the coordinates of a point within the list box.  
  
 *bAutoScroll*  
 Nonzero if scrolling is allowed, otherwise 0.  
  
### <a name="return-value"></a>Return Value  
 Zero-based index of the drag list box item.  
  
## <a name="see-also"></a>See Also  
 [MFC Sample TSTCON](../../visual-cpp-samples.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)

