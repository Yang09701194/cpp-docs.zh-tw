---
title: rts_alloc Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
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
ms.openlocfilehash: f3eb62d14b304decfe168b224f87f433ac0c39d9
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="rtsalloc-class"></a>rts_alloc Class
The rts_alloc template class describes a [filter](../standard-library/allocators-header.md) that holds an array of cache instances and determines which instance to use for allocation and deallocation at runtime instead of at compile time.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Cache>  
class rts_alloc
```  
  
#### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Cache`|The type of cache instances contained in the array. This can be [cache_chunklist Class](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), or [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## <a name="remarks"></a>Remarks  
 This template class holds multiple block allocator instances and determines which instance to use for allocation or deallocation at runtime instead of at compile time. It is used with compilers that cannot compile rebind.  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[allocate](#allocate)|Allocates a block of memory.|  
|[deallocate](#deallocate)|Frees a specified number of objects from storage beginning at a specified position.|  
|[equals](#equals)|Compares two caches for equality.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a>  rts_alloc::allocate  
 Allocates a block of memory.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`count`|The number of elements in the array to be allocated.|  
  
### <a name="return-value"></a>Return Value  
 A pointer to the allocated object.  
  
### <a name="remarks"></a>Remarks  
 The member function returns `caches[_IDX].allocate(count)`, where the index `_IDX` is determined by the requested block size `count`, or, if `count` is too large, it returns `operator new(count)`. `cache`, which represents the cache object.  
  
##  <a name="deallocate"></a>  rts_alloc::deallocate  
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
 The member function calls `caches[_IDX].deallocate(ptr, count)`, where the index `_IDX` is determined by the requested block size `count`, or, if `count` is too large, it returns `operator delete(ptr)`.  
  
##  <a name="equals"></a>  rts_alloc::equals  
 Compares two caches for equality.  
  
```
bool equals(const sync<_Cache>& _Other) const;
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`_Cache`|The cache object associated with the filter.|  
|`_Other`|The cache object to compare for equality.|  
  
### <a name="remarks"></a>Remarks  
 `true` if the result of `caches[0].equals(other.caches[0])`; otherwise, `false`. `caches` represents the array of cache objects.  
  
## <a name="see-also"></a>See Also  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)   
 [\<allocators>](../standard-library/allocators-header.md)




