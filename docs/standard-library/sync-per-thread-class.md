---
title: sync_per_thread Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_per_thread
- stdext::sync_per_thread [C++], allocate
- stdext::sync_per_thread [C++], deallocate
- stdext::sync_per_thread [C++], equals
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 8d0f0ca6f449e1b220f553f8f1ba378abf43069a
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="syncperthread-class"></a>sync_per_thread Class
Describes a [synchronization filter](../standard-library/allocators-header.md) that provides a separate cache object for each thread.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Cache>  
class sync_per_thread
```  
  
#### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Cache`|The type of cache associated with the synchronization filter. This can be [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), or [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## <a name="remarks"></a>Remarks  
 Allocators that use `sync_per_thread` can compare equal even though blocks allocated in one thread cannot be deallocated from another thread. When using one of these allocators memory blocks allocated in one thread should not be made visible to other threads. In practice this means that a container that uses one of these allocators should only be accessed by a single thread.  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[allocate](#allocate)|Allocates a block of memory.|  
|[deallocate](#deallocate)|Frees a specified number of objects from storage beginning at a specified position.|  
|[equals](#equals)|Compares two caches for equality.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a>  sync_per_thread::allocate  
 Allocates a block of memory.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`count`|The number of elements in the array to be allocated.|  
  
### <a name="remarks"></a>Remarks  
 The member function returns the result of a call to `cache::allocate(count)` on the cache object belonging to the current thread. If no cache object has been allocated for the current thread, it first allocates one.  
  
##  <a name="deallocate"></a>  sync_per_thread::deallocate  
 Frees a specified number of objects from storage beginning at a specified position.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`ptr`|A pointer to the first object to be deallocated from storage.|  
|`count`|The number of objects to be deallocated from storage.|  
  
### <a name="remarks"></a>Remarks  
 The member function calls `deallocate` on the cache object belonging to the current thread. If no cache object has been allocated for the current thread, it first allocates one.  
  
##  <a name="equals"></a>  sync_per_thread::equals  
 Compares two caches for equality.  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Cache`|The cache object of the synchronization filter.|  
|`Other`|The cache object to compare for equality.|  
  
### <a name="return-value"></a>Return Value  
 `false` if no cache object has been allocated for this object or for `Other` in the current thread. Otherwise it returns the result of applying `operator==` to the two cache objects.  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>See Also  
 [\<allocators>](../standard-library/allocators-header.md)




