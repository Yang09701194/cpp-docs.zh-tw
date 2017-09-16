---
title: sync_none Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
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
ms.openlocfilehash: 086bf59fa51ee86e14bdb981796587023a034d89
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="syncnone-class"></a>sync_none Class
Describes a [synchronization filter](../standard-library/allocators-header.md) that provides no synchronization.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Cache>  
class sync_none
```  
  
#### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Cache`|The type of cache associated with the synchronization filter. This can be [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), or [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[allocate](#allocate)|Allocates a block of memory.|  
|[deallocate](#deallocate)|Frees a specified number of objects from storage beginning at a specified position.|  
|[equals](#equals)|Compares two caches for equality.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a>  sync_none::allocate  
 Allocates a block of memory.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`count`|The number of elements in the array to be allocated.|  
  
### <a name="remarks"></a>Remarks  
 The member function returns `cache.allocate(count)`, where `cache` is the cache object.  
  
##  <a name="deallocate"></a>  sync_none::deallocate  
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
 The member function calls `cache.deallocate(ptr, count)`, where `cache` represents the cache object.  
  
##  <a name="equals"></a>  sync_none::equals  
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
 The member function always returns `true`.  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>See Also  
 [\<allocators>](../standard-library/allocators-header.md)




