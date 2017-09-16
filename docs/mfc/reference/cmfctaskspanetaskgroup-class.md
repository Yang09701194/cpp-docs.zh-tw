---
title: CMFCTasksPaneTaskGroup Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
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
ms.openlocfilehash: a7c7503acf4deed60ab86eac6c91c64f746c8a09
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup Class
The `CMFCTasksPaneTaskGroup` class is a helper class used by the [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) control. Objects of type `CMFCTasksPaneTaskGroup` represent a *task group*. The task group is a list of items that the framework displays in a separate box that has a collapse button. The box can have an optional caption (group name). If a group is collapsed, the list of tasks is not visible.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Constructs a `CMFCTasksPaneTaskGroup` object.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Destructor.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Determines the accessibility data for the current task group.|  
  
### <a name="data-members"></a>Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Determines whether the task group is aligned to the bottom of the task pane control.|  
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Determines whether the task group is collapsed.|  
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Determines whether the task group is *special.* The framework displays special captions in a different color.|  
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Contains the internal list of tasks.|  
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Specifies the bounding rectangle of the group caption.|  
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Specifies the bounding rectangle of the group.|  
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Specifies the name of the group.|  
  
## <a name="remarks"></a>Remarks  
 The following illustration shows an expanded task group:  
  
 ![Task group, expanded](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
 The following illustration shows a collapsed task group:  
  
 ![Collapsed task group](../../mfc/reference/media/nexttaskgrpcollapse.png "nexttaskgrpcollapse")  
  
 The following illustration shows a task group without a caption:  
  
 ![Task group without a caption](../../mfc/reference/media/nexttaskgrpnocapt.png "nexttaskgrpnocapt")  
  
 The following illustration shows two task groups. The first task group is marked as special by setting the `m_bIsSpecial` flag to `TRUE`, while the second task group is not special. Note how the caption for the first task group is darker than the second task group:  
  
 ![Special task group](../../mfc/reference/media/nexttaskgrpspecial.png "nexttaskgrpspecial")  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetaskgroup"></a>  CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup  
 Constructs a `CMFCTasksPaneTaskGroup` object.  
  
```  
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,  
    BOOL bIsBottom,  
    BOOL bIsSpecial=FALSE,  
    BOOL bIsCollapsed=FALSE,  
    CMFCTasksPanePropertyPage* pPage=NULL,  
    HICON hIcon=NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lpszName`  
 Specifies the name of the group in the group caption.  
  
 `bIsBottom`  
 Specifies whether the group is aligned to the bottom of the task pane control.  
  
 `bIsSpecial`  
 Specifies whether the group is designated as *special* and thus, whether the group caption is filled with a different color.  
  
 `bIsCollapsed`  
 Specifies whether the group is collapsed.  
  
 `pPage`  
 Specifies the property page that this task group belongs to.  
  
 `hIcon`  
 Specifies the icon that displays in the group caption.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_bisbottom"></a>  CMFCTasksPaneTaskGroup::m_bIsBottom  
 Determines whether the task group is aligned to the bottom of the task pane control.  
  
```  
BOOL m_bIsBottom;  
```  
  
### <a name="remarks"></a>Remarks  
 Only one group can be aligned to the bottom of the task pane control. This task group must be added last. For more information, see [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_biscollapsed"></a>  CMFCTasksPaneTaskGroup::m_bIsCollapsed  
 Determines whether the task group is collapsed.  
  
```  
BOOL m_bIsCollapsed;  
```  
  
### <a name="remarks"></a>Remarks  
 You can enable or disable the ability to collapse groups on the task pane by calling [CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).  
  
##  <a name="m_bisspecial"></a>  CMFCTasksPaneTaskGroup::m_bIsSpecial  
 Determines whether the task group is *special* and whether the caption for a special task group should be identified by a different color.  
  
```  
BOOL m_bIsSpecial;  
```  
  
### <a name="remarks"></a>Remarks  
 If your application is using the Windows XP visual theme and `m_bIsSpecial` is `FALSE`, the framework calls `DrawThemeBackground` with the `EBP_NORMALGROUPBACKGROUND` flag. If `m_bIsSpecial` is `TRUE`, the framework calls `DrawThemeBackground` with the `EBP_SPECIALGROUPBACKGROUND` flag.  
  
##  <a name="m_lsttasks"></a>  CMFCTasksPaneTaskGroup::m_lstTasks  
 Contains the internal list of tasks.  
  
```  
CObList m_lstTasks;  
```  
  
### <a name="remarks"></a>Remarks  
 To fill this list, call [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).  
  
##  <a name="m_rect"></a>  CMFCTasksPaneTaskGroup::m_rect  
 Specifies the bounding rectangle of the group caption.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Remarks  
 This value is automatically calculated by the framework.  
  
##  <a name="m_rectgroup"></a>  CMFCTasksPaneTaskGroup::m_rectGroup  
 Specifies the bounding rectangle of the group.  
  
```  
CRect m_rectGroup;  
```  
  
### <a name="remarks"></a>Remarks  
 This value is calculated automatically by the framework.  
  
##  <a name="m_strname"></a>  CMFCTasksPaneTaskGroup::m_strName  
 Specifies the name of the group.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Remarks  
 If this value is empty, the group caption is not displayed and the group cannot be collapsed.  
  
##  <a name="setaccdata"></a>  CMFCTasksPaneTaskGroup::SetACCData  
 Determines the accessibility data for the current task group.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameters  
 [in] `pParent`  
 Represents the parent window of the current task group.  
  
 [out] `data`  
 An object of type `CAccessibilityData` that is populated with the accessibility data of the current task group.  
  
### <a name="return-value"></a>Return Value  
 `TRUE` if the `data` parameter was successfully populated with the accessibility data of the current task group; otherwise, `FALSE`.  
  
## <a name="see-also"></a>See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPane Class](../../mfc/reference/cmfctaskspane-class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)

