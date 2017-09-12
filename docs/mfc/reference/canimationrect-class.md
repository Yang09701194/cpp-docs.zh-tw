---
title: CAnimationRect Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
caps.latest.revision: 17
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
ms.openlocfilehash: 9a8705bdf9caca25284a9364de297a0fbab57c3c
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="canimationrect-class"></a>CAnimationRect Class
Implements the functionality of a rectangle whose sides can be animated.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|Overloaded. Constructs an animation rect object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|Adds transitions for left, top, right and bottom coordinates.|  
|[CAnimationRect::GetBottom](#getbottom)|Provides access to CAnimationVariable representing bottom coordinate.|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Returns the default values for rectangle's bounds.|  
|[CAnimationRect::GetLeft](#getleft)|Provides access to CAnimationVariable representing left coordinate.|  
|[CAnimationRect::GetRight](#getright)|Provides access to CAnimationVariable representing right coordinate.|  
|[CAnimationRect::GetTop](#gettop)|Provides access to CAnimationVariable representing top coordinate.|  
|[CAnimationRect::GetValue](#getvalue)|Returns current value.|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Sets default value.|  
  
### <a name="protected-methods"></a>Protected Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Puts the encapsulated animation variables into a list. (Overrides [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|Converts a CAnimationRect to RECT.|  
|[CAnimationRect::operator=](#operator_eq)|Assigns rect to CAnimationRect.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Specifies whether the rectangle has fixed size.|  
  
### <a name="protected-data-members"></a>Protected Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|The encapsulated animation variable that represents Bottom bound of animation rectangle.|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|The encapsulated animation variable that represents Left bound of animation rectangle.|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|The encapsulated animation variable that represents Right bound of animation rectangle.|  
|[CAnimationRect::m_szInitial](#m_szinitial)|Specifies initial size of animation rectangle.|  
|[CAnimationRect::m_topValue](#m_topvalue)|The encapsulated animation variable that represents Top bound of animation rectangle.|  
  
## <a name="remarks"></a>Remarks  
 The CAnimationRect class encapsulates four CAnimationVariable objects and can represent in applications a rectangle. To use this class in application, just instantiate an object of this class, add it to animation controller using CAnimationController::AddAnimationObject and call AddTransition for each transition to be applied to left, right top and bottom coordinates.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationRect::AddTransition  
 Adds transitions for left, top, right and bottom coordinates.  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>Parameters  
 `pLeftTransition`  
 Specifies transition for the left side.  
  
 `pTopTransition`  
 Specifies transition for the top side.  
  
 `pRightTransition`  
 Specifies transition for the right side.  
  
 `pBottomTransition`  
 Specifies transition for the bottom side.  
  
### <a name="remarks"></a>Remarks  
 Call this function to add the specified transitions to the internal list of transitions to be applied to animation variables for each rectangle sides. When you add transitions, they are not applied immediately and stored in an internal list. Transitions are applied (added to a storyboard for a particular value) when you call CAnimationController::AnimateGroup. If you don't need to apply a transition to one of the rectangle sides, you can pass NULL.  
  
##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect  
 Constructs a CAnimationRect object.  
  
```  
CAnimationRect();

 
CAnimationRect(
    const CRect& rect,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    const CPoint& pt,  
    const CSize& sz,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    int nLeft,  
    int nTop,  
    int nRight,  
    int nBottom,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameters  
 `rect`  
 Specifies default rectangle.  
  
 `nGroupID`  
 Specifies Group ID.  
  
 `nObjectID`  
 Specifies Object ID.  
  
 `dwUserData`  
 Specifies user-defined data.  
  
 `pt`  
 Coordinate of top-left corner.  
  
 `sz`  
 Size of rectangle.  
  
 `nLeft`  
 Specifies coordinate of left bound.  
  
 `nTop`  
 Specifies coordinate of top bound.  
  
 `nRight`  
 Specifies coordinate of right bound.  
  
 `nBottom`  
 Specifies coordinate of bottom bound.  
  
### <a name="remarks"></a>Remarks  
 The object is constructed with default values for left, top, right and bottom, Object ID and Group ID, which will be set to 0. They can be changed later at runtime using SetDefaultValue and SetID.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList  
 Puts the encapsulated animation variables into a list.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameters  
 `lst`  
 When the function returns, it contains pointers to four CAnimationVariable objects representing coordinates of rectangle.  
  
##  <a name="getbottom"></a>  CAnimationRect::GetBottom  
 Provides access to CAnimationVariable representing bottom coordinate.  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>Return Value  
 A reference to encapsulated CAnimationVariable representing bottom coordinate.  
  
### <a name="remarks"></a>Remarks  
 You can call this method to get direct access to underlying CAnimationVariable representing the bottom coordinate.  
  
##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue  
 Returns the default values for rectangle's bounds.  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>Return Value  
 A CRect value containing defaults for left, right, top and bottom.  
  
### <a name="remarks"></a>Remarks  
 Call this function to retrieve default value, which was previously set by constructor or SetDefaultValue.  
  
##  <a name="getleft"></a>  CAnimationRect::GetLeft  
 Provides access to CAnimationVariable representing left coordinate.  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>Return Value  
 A reference to encapsulated CAnimationVariable representing left coordinate.  
  
### <a name="remarks"></a>Remarks  
 You can call this method to get direct access to underlying CAnimationVariable representing the left coordinate.  
  
##  <a name="getright"></a>  CAnimationRect::GetRight  
 Provides access to CAnimationVariable representing right coordinate.  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>Return Value  
 A reference to encapsulated CAnimationVariable representing right coordinate.  
  
### <a name="remarks"></a>Remarks  
 You can call this method to get direct access to underlying CAnimationVariable representing the right coordinate.  
  
##  <a name="gettop"></a>  CAnimationRect::GetTop  
 Provides access to CAnimationVariable representing top coordinate.  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>Return Value  
 A reference to encapsulated CAnimationVariable representing top coordinate.  
  
### <a name="remarks"></a>Remarks  
 You can call this method to get direct access to underlying CAnimationVariable representing the top coordinate.  
  
##  <a name="getvalue"></a>  CAnimationRect::GetValue  
 Returns current value.  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>Parameters  
 `rect`  
 Output. Contains the current value when this method returns.  
  
### <a name="return-value"></a>Return Value  
 TRUE, if the current value was successfully retrieved; otherwise FALSE.  
  
### <a name="remarks"></a>Remarks  
 Call this function to retrieve the current value of animation rectangle. If this method fails or underlying COM objects for left, top, right and bottom have not been initialized, rect contains default value, which was previously set in constructor or by SetDefaultValue.  
  
##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize  
 Specifies whether the rectangle has fixed size.  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>Remarks  
 If this member is true, then the size of rectangle is fixed and right and bottom values are recalculated each time the top-left corner is moved according to the fixed size. Set this value to TRUE to easily move the rectangle around the screen. In this case transitions applied to right and bottom coordinates are ignored. The size is stored internally when you construct the object and/or call SetDefaultValue. By default this member is set to FALSE.  
  
##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue  
 The encapsulated animation variable that represents Bottom bound of animation rectangle.  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue  
 The encapsulated animation variable that represents Left bound of animation rectangle.  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue  
 The encapsulated animation variable that represents Right bound of animation rectangle.  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial  
 Specifies initial size of animation rectangle.  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue  
 The encapsulated animation variable that represents Top bound of animation rectangle.  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="operator_rect"></a>  CAnimationRect::operator RECT  
 Converts a CAnimationRect to RECT.  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>Return Value  
 Current value of animation rectangle as RECT.  
  
### <a name="remarks"></a>Remarks  
 This function internally calls GetValue. If GetValue for some reason fails, the returned RECT will contain default values for all rectangle coordinates.  
  
##  <a name="operator_eq"></a>  CAnimationRect::operator=  
 Assigns rect to CAnimationRect.  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>Parameters  
 `rect`  
 The new value of animation rectangle.  
  
### <a name="remarks"></a>Remarks  
 It's recommended to do that before animation start, because this operator calls SetDefaultValue, which recreates the underlying COM objects for color components if they have been created. If you subscribed this animation object to events (ValueChanged or IntegerValueChanged), you need to re-enable these events.  
  
##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue  
 Sets default value.  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>Parameters  
 `rect`  
 Specifies new default values for left, top, right and bottom.  
  
### <a name="remarks"></a>Remarks  
 Use this function to set a default value to animation object. This methods assigns default values to rectangle's bounds. It also recreates underlying COM objects if they have been created. If you subscribed this animation object to events (ValueChanged or IntegerValueChanged), you need to re-enable these events.  
  
## <a name="see-also"></a>See Also  
 [Classes](../../mfc/reference/mfc-classes.md)

