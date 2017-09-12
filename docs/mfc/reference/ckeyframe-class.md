---
title: CKeyFrame Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
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
ms.openlocfilehash: 0f7fbeccae04eaeb02be295c45b33db20144f115
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="ckeyframe-class"></a>CKeyFrame Class
Represents an animation keyframe.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|Overloaded. Constructs a keyframe that depends on other keyframe.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Adds a keyframe to a storyboard. (Overrides [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Adds a keyframe to storyboard after transition.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Adds a keyframe to storyboard at offset.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Returns a pointer to a keyframe this keyframe depends on.|  
|[CKeyFrame::GetOffset](#getoffset)|Returns an offset from other keyframe.|  
|[CKeyFrame::GetTransition](#gettransition)|Returns a pointer to a transition this keyframe depends on.|  
  
### <a name="protected-data-members"></a>Protected Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|Specifies offset of this keyframe from a keyframe stored in m_pExistingKeyFrame.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Stores a pointer to an existing keframe. This keyframe is added to storyboard with m_offset to the existing keyframe.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|Stores a pointer to transtion that begins at this keyframe.|  
  
## <a name="remarks"></a>Remarks  
 This class implements an animation keyframe. A keyframe represents a moment in time within a storyboard and can be used to specify the start and end times of transitions. A keyframe may be based on other keyframe and have an offset (in seconds) from it, or may be based on a transition and represent a moment in time when this transition ends.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard  
 Adds a keyframe to a storyboard.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameters  
 `pStoryboard`  
 A pointer to a storyboard.  
  
 `bDeepAdd`  
 Specifies whether to add keyframe or transition recursively.  
  
### <a name="return-value"></a>Return Value  
 TRUE, if keyframe was added successfully.  
  
### <a name="remarks"></a>Remarks  
 This method adds a keyframe to storyboard. If it depends on other keyframe or transition and bDeepAdd is TRUE, this method tries to add them recursively.  
  
##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition  
 Adds a keyframe to storyboard after transition.  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameters  
 `pStoryboard`  
 A pointer to a storyboard.  
  
 `bDeepAdd`  
 Specifies whether to add a transition recursively.  
  
### <a name="return-value"></a>Return Value  
 TRUE, if keyframe was added successfully.  
  
### <a name="remarks"></a>Remarks  
 This function is called by the framework to add a keyframe to storyboard after transition.  
  
##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset  
 Adds a keyframe to storyboard at offset.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Parameters  
 `pStoryboard`  
 A pointer to a storyboard.  
  
 `bDeepAdd`  
 Specifies whether to add a keyframe this keyframe depend on recursively.  
  
### <a name="return-value"></a>Return Value  
 TRUE, if keyframe was added successfully.  
  
### <a name="remarks"></a>Remarks  
 This function is called by the framework to add a keyframe to storyboard at offset.  
  
##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame  
 Constructs a keyframe that depends on a transition.  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Parameters  
 `pTransition`  
 A pointer to a transition.  
  
 `pKeyframe`  
 A pointer to keyframe.  
  
 `offset`  
 Offset, in seconds, from keyframe specified by pKeyframe.  
  
### <a name="remarks"></a>Remarks  
 The constructed keyframe will represent a moment in time within a storyboard when the specified transition ends.  
  
##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe  
 Returns a pointer to a keyframe this keyframe depends on.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>Return Value  
 A valid pointer to keyframe, or NULL if this keyframe does not depend on other keyframe.  
  
### <a name="remarks"></a>Remarks  
 This is an accessor to a keyframe this keyframe depends on.  
  
##  <a name="getoffset"></a>  CKeyFrame::GetOffset  
 Returns an offset from other keyframe.  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>Return Value  
 An offset in seconds from other keyframe.  
  
### <a name="remarks"></a>Remarks  
 This method should be called to determine an offset in seconds from other keyframe.  
  
##  <a name="gettransition"></a>  CKeyFrame::GetTransition  
 Returns a pointer to a transition this keyframe depends on.  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>Return Value  
 A valid pointer to transition, or NULL if this keyframe does not depend on transition.  
  
### <a name="remarks"></a>Remarks  
 This is an accessor to a transition this keyframe depends on.  
  
##  <a name="m_offset"></a>  CKeyFrame::m_offset  
 Specifies offset of this keyframe from a keyframe stored in m_pExistingKeyFrame.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame  
 Stores a pointer to an existing keframe. This keyframe is added to storyboard with m_offset to the existing keyframe.  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition  
 Stores a pointer to transtion that begins at this keyframe.  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>See Also  
 [Classes](../../mfc/reference/mfc-classes.md)

