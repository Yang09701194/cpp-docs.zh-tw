---
title: CD2DLayer Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
dev_langs:
- C++
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
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
ms.openlocfilehash: 7fe4cf3c4d660ca9ff03db98fb4c08b869fb9c1e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cd2dlayer-class"></a>CD2DLayer Class
A wrapper for ID2D1Layer.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Constructs a CD2DLayer object.|  
|[CD2DLayer::~CD2DLayer](#_dtorcd2dlayer)|The destructor. Called when a D2D layer object is being destroyed.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DLayer::Attach](#attach)|Attaches existing resource interface to the object|  
|[CD2DLayer::Create](#create)|Creates a CD2DLayer. (Overrides [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLayer::Destroy](#destroy)|Destroys a CD2DLayer object. (Overrides [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DLayer::Detach](#detach)|Detaches resource interface from the object|  
|[CD2DLayer::Get](#get)|Returns ID2D1Layer interface|  
|[CD2DLayer::GetSize](#getsize)|Returns the size of the render target in device-independent pixels|  
|[CD2DLayer::IsValid](#isvalid)|Checks resource validity (Overrides [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
  
### <a name="public-operators"></a>Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DLayer::operator ID2D1Layer*](#operator_id2d1layer_star)|Returns ID2D1Layer interface|  
  
### <a name="protected-data-members"></a>Protected Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DLayer::m_pLayer](#m_player)|Stores a pointer to an ID2D1Layer object.|  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DLayer`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dlayer"></a>  CD2DLayer::~CD2DLayer  
 The destructor. Called when a D2D layer object is being destroyed.  
  
```  
virtual ~CD2DLayer();
```  
  
##  <a name="attach"></a>  CD2DLayer::Attach  
 Attaches existing resource interface to the object  
  
```  
void Attach(ID2D1Layer* pResource);
```  
  
### <a name="parameters"></a>Parameters  
 `pResource`  
 Existing resource interface. Cannot be NULL  
  
##  <a name="cd2dlayer"></a>  CD2DLayer::CD2DLayer  
 Constructs a CD2DLayer object.  
  
```  
CD2DLayer(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameters  
 `pParentTarget`  
 A pointer to the render target.  
  
 `bAutoDestroy`  
 Indicates that the object will be destroyed by owner (pParentTarget).  
  
##  <a name="create"></a>  CD2DLayer::Create  
 Creates a CD2DLayer.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameters  
 `pRenderTarget`  
 A pointer to the render target.  
  
### <a name="return-value"></a>Return Value  
 If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.  
  
##  <a name="destroy"></a>  CD2DLayer::Destroy  
 Destroys a CD2DLayer object.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DLayer::Detach  
 Detaches resource interface from the object  
  
```  
ID2D1Layer* Detach();
```  
  
### <a name="return-value"></a>Return Value  
 Pointer to detached resource interface.  
  
##  <a name="get"></a>  CD2DLayer::Get  
 Returns ID2D1Layer interface  
  
```  
ID2D1Layer* Get();
```  
  
### <a name="return-value"></a>Return Value  
 Pointer to an ID2D1Layer interface or NULL if object is not initialized yet.  
  
##  <a name="getsize"></a>  CD2DLayer::GetSize  
 Returns the size of the render target in device-independent pixels  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Return Value  
 The current size of the render target in device-independent pixels  
  
##  <a name="isvalid"></a>  CD2DLayer::IsValid  
 Checks resource validity  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Return Value  
 TRUE if resource is valid; otherwise FALSE.  
  
##  <a name="m_player"></a>  CD2DLayer::m_pLayer  
 Stores a pointer to an ID2D1Layer object.  
  
```  
ID2D1Layer* m_pLayer;  
```  
  
##  <a name="operator_id2d1layer_star"></a>  CD2DLayer::operator ID2D1Layer*  
 Returns ID2D1Layer interface  
  
```  
operator ID2D1Layer* ();
```  
  
### <a name="return-value"></a>Return Value  
 Pointer to an ID2D1Layer interface or NULL if object is not initialized yet.  
  
## <a name="see-also"></a>See Also  
 [Classes](../../mfc/reference/mfc-classes.md)

