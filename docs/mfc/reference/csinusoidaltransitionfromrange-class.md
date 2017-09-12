---
title: CSinusoidalTransitionFromRange Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
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
ms.openlocfilehash: 0f781fc168d420bd180442c3bfdc88024b7fb826
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange Class
Encapsulates a sinusoidal-range transition that has a given range of oscillation.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Constructs a transition object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::Create](#create)|Calls the transition library to create encapsulated transition COM object. (Overrides [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|The value of the animation variable at a peak of the sinusoidal wave.|  
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|The value of the animation variable at a trough of the sinusoidal wave.|  
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|The duration of the transition.|  
|[CSinusoidalTransitionFromRange::m_period](#m_period)|The period of oscillation of the sinusoidal wave in seconds.|  
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|The slope at the start of the transition.|  
  
## <a name="remarks"></a>Remarks  
 The value of the animation variable fluctuates between the specified minimum and maximum values over the entire duration of a sinusoidal-range transition. The slope parameter is used to disambiguate between the two possible sine waves specified by the other parameters. Because all transitions are cleared automatically, it's recommended to allocated them using operator new. The encapsulated IUIAnimationTransition COM object is created by CAnimationController::AnimateGroup, until then it's NULL. Changing member variables after creation of this COM object has no effect.  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxanimationcontroller.h  
  
##  <a name="create"></a>  CSinusoidalTransitionFromRange::Create  
 Calls the transition library to create encapsulated transition COM object.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameters  
 `pLibrary`  
 A pointer to transition library, which is responsible for creation of standard transitions.  
  
### <a name="return-value"></a>Return Value  
 TRUE if transition is created successfully; otherwise FALSE.  
  
##  <a name="csinusoidaltransitionfromrange"></a>  CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange  
 Constructs a transition object.  
  
```  
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblMinimumValue,  
    DOUBLE dblMaximumValue,  
    UI_ANIMATION_SECONDS period,  
    UI_ANIMATION_SLOPE slope);
```  
  
### <a name="parameters"></a>Parameters  
 `duration`  
 The duration of the transition.  
  
 `dblMinimumValue`  
 The value of the animation variable at a trough of the sinusoidal wave.  
  
 `dblMaximumValue`  
 The value of the animation variable at a peak of the sinusoidal wave.  
  
 `period`  
 The period of oscillation of the sinusoidal wave in seconds.  
  
 `slope`  
 The slope at the start of the transition.  
  
##  <a name="m_dblmaximumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMaximumValue  
 The value of the animation variable at a peak of the sinusoidal wave.  
  
```  
DOUBLE m_dblMaximumValue;  
```  
  
##  <a name="m_dblminimumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMinimumValue  
 The value of the animation variable at a trough of the sinusoidal wave.  
  
```  
DOUBLE m_dblMinimumValue;  
```  
  
##  <a name="m_duration"></a>  CSinusoidalTransitionFromRange::m_duration  
 The duration of the transition.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>  CSinusoidalTransitionFromRange::m_period  
 The period of oscillation of the sinusoidal wave in seconds.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
##  <a name="m_slope"></a>  CSinusoidalTransitionFromRange::m_slope  
 The slope at the start of the transition.  
  
```  
UI_ANIMATION_SLOPE m_slope;  
```  
  
## <a name="see-also"></a>See Also  
 [Classes](../../mfc/reference/mfc-classes.md)

