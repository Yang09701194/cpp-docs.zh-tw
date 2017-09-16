---
title: CSyncObject Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
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
ms.openlocfilehash: e73fe4c85e6614a4e1901b02cbfd4917e016503c
ms.contentlocale: zh-tw
ms.lasthandoff: 09/12/2017

---
# <a name="csyncobject-class"></a>CSyncObject Class
A pure virtual class that provides functionality common to the synchronization objects in Win32.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|Constructs a `CSyncObject` object.|  
  
### <a name="public-methods"></a>Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|Gains access to the synchronization object.|  
|[CSyncObject::Unlock](#unlock)|Gains access to the synchronization object.|  
  
### <a name="public-operators"></a>Public Operators  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::operator HANDLE](#operator_handle)|Provides access to the synchronization object.|  
  
### <a name="public-data-members"></a>Public Data Members  
  
|Name|Description|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|The handle to the underlying synchronization object.|  
  
## <a name="remarks"></a>Remarks  
 The Microsoft Foundation Class Library provides several classes derived from `CSyncObject`. These are [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), and [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 For information on how to use the synchronization objects, see the article [Multithreading: How to Use the Synchronization Classes](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Inheritance Hierarchy  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>Requirements  
 **Header:** afxmt.h  
  
##  <a name="csyncobject"></a>  CSyncObject::CSyncObject  
 Constructs a synchronization object with the supplied name.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>Parameters  
 `pstrName`  
 The name of the object. If **NULL**, *pstrName* will be null.  
  
##  <a name="lock"></a>  CSyncObject::Lock  
 Call this function to gain access to the resource controlled by the synchronization object.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>Parameters  
 `dwTimeout`  
 Specifies the amount of time in milliseconds to wait for the synchronization object to be available (signaled). If **INFINITE**, `Lock` will wait until the object is signaled before returning.  
  
### <a name="return-value"></a>Return Value  
 Nonzero if the function was successful; otherwise 0.  
  
### <a name="remarks"></a>Remarks  
 If the synchronization object is signaled, `Lock` will return successfully and the thread now owns the object. If the synchronization object is nonsignaled (unavailable), `Lock` will wait for the synchronization object to become signaled up to the number of milliseconds specified in the *dwTimeOut* parameter. If the synchronization object did not become signaled in the specified amount of time, `Lock` returns failure.  
  
##  <a name="m_hobject"></a>  CSyncObject::m_hObject  
 The handle to the underlying synchronization object.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>  CSyncObject::operator HANDLE  
 Use this operator to get the handle of the `CSyncObject` object.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Return Value  
 If successful, the handle of the synchronization object; otherwise, **NULL**.  
  
### <a name="remarks"></a>Remarks  
 You can use the handle to call Windows APIs directly.  
  
##  <a name="unlock"></a>  CSyncObject::Unlock  
 The declaration of `Unlock` with no parameters is a pure virtual function, and must be overridden by all classes deriving from `CSyncObject`.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parameters  
 `lCount`  
 Not used by default implementation.  
  
 `lpPrevCount`  
 Not used by default implementation.  
  
### <a name="return-value"></a>Return Value  
 Default implementation always returns **TRUE**.  
  
### <a name="remarks"></a>Remarks  
 The default implementation of the declaration with two parameters always returns **TRUE**. This function is called to release access to the synchronization object owned by the calling thread. The second declaration is provided for synchronization objects such as semaphores that allow more than one access of a controlled resource.  
  
## <a name="see-also"></a>See Also  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)




