---
title: CD2DResource Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
dev_langs:
- C++
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
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
ms.openlocfilehash: 8b329c569fa44a5c4967f8cb65c65b15577be670
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="cd2dresource-class"></a>CD2DResource Class
An abstract class that provides a interface for creating and managing D2D resources such as brushes, layers, and texts.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DResource : public CObject;  
```  
  
## <a name="members"></a>Members  
  
### <a name="protected-constructors"></a>Protected Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DResource::CD2DResource](#cd2dresource)|Constructs a CD2DResource object.|  
|[CD2DResource::~CD2DResource](#cd2dresource__~cd2dresource)|The destructor. Called when a D2D resource object is being destroyed.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DResource::Create](#create)|Creates a CD2DResource.|  
|[CD2DResource::Destroy](#destroy)|Destroys a CD2DResource object.|  
|[CD2DResource::IsValid](#isvalid)|Checks resource validity|  
  
### <a name="protected-methods"></a>Protected Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DResource::IsAutoDestroy](#isautodestroy)|Check auto destroy flag.|  
|[CD2DResource::ReCreate](#recreate)|Re-creates a CD2DResource.|  
  
### <a name="protected-data-members"></a>Protected Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|Resource will be destoyed by owner (CRenderTarget)|  
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|Pointer to the parent CRenderTarget)|  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CD2DResource`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dresource"></a>  CD2DResource::~CD2DResource  
 The destructor. Called when a D2D resource object is being destroyed.  
  
```  
virtual ~CD2DResource();
```  
  
##  <a name="cd2dresource"></a>  CD2DResource::CD2DResource  
 Constructs a CD2DResource object.  
  
```  
CD2DResource(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy);
```  
  
### <a name="parameters"></a>Parameters  
 `pParentTarget`  
 A pointer to the render target.  
  
 `bAutoDestroy`  
 Indicates that the object will be destroyed by owner (pParentTarget).  
  
##  <a name="create"></a>  CD2DResource::Create  
 Creates a CD2DResource.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;  
```  
  
### <a name="parameters"></a>Parameters  
 `pRenderTarget`  
 A pointer to the render target.  
  
### <a name="return-value"></a>Return Value  
 If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.  
  
##  <a name="destroy"></a>  CD2DResource::Destroy  
 Destroys a CD2DResource object.  
  
```  
virtual void Destroy() = 0;  
```  
  
##  <a name="isautodestroy"></a>  CD2DResource::IsAutoDestroy  
 Check auto destroy flag.  
  
```  
BOOL IsAutoDestroy() const;  
```  
  
### <a name="return-value"></a>Return Value  
 TRUE if the object will be destroyed by its owner; otherwise FALSE.  
  
##  <a name="isvalid"></a>  CD2DResource::IsValid  
 Checks resource validity  
  
```  
virtual BOOL IsValid() const = 0;  
```  
  
### <a name="return-value"></a>Return Value  
 TRUE if resource is valid; otherwise FALSE.  
  
##  <a name="m_bisautodestroy"></a>  CD2DResource::m_bIsAutoDestroy  
 Resource will be destoyed by owner (CRenderTarget)  
  
```  
BOOL m_bIsAutoDestroy;  
```  
  
##  <a name="m_pparenttarget"></a>  CD2DResource::m_pParentTarget  
 Pointer to the parent CRenderTarget)  
  
```  
CRenderTarget* m_pParentTarget;  
```  
  
##  <a name="recreate"></a>  CD2DResource::ReCreate  
 Re-creates a CD2DResource.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameters  
 `pRenderTarget`  
 A pointer to the render target.  
  
### <a name="return-value"></a>Return Value  
 If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.  
  
## <a name="see-also"></a>See Also  
 [Classes](../../mfc/reference/mfc-classes.md)

