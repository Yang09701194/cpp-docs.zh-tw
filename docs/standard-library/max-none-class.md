---
title: max_none Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 2ecc4f3e90e9749e109f48577f4ff8e64e055718
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="maxnone-class"></a>max_none Class
Describes a [max class](../standard-library/allocators-header.md) object that limits a [freelist](../standard-library/freelist-class.md) object to a maximum length of zero.  
  
## <a name="syntax"></a>Syntax  
  
```
template <std::size_t Max>  
class max_none
```  
  
#### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`Max`|The max class that determines the maximum number of elements to store in the `freelist`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[allocated](#allocated)|Increments the count of allocated memory blocks.|  
|[deallocated](#deallocated)|Decrements the count of allocated memory blocks.|  
|[full](#full)|Returns a value that specifies whether more memory blocks should be added to the free list.|  
|[released](#released)|Decrements the count of memory blocks on the free list.|  
|[saved](#saved)|Increments the count of memory blocks on the free list.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocated"></a>  max_none::allocated  
 Increments the count of allocated memory blocks.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`_Nx`|The increment value.|  
  
### <a name="remarks"></a>Remarks  
 This member function does nothing. It is called after each successful call by `cache_freelist::allocate` to operator `new`. The argument `_Nx` is the number of memory blocks in the chunk allocated by operator `new`.  
  
##  <a name="deallocated"></a>  max_none::deallocated  
 Decrements the count of allocated memory blocks.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`_Nx`|The increment value.|  
  
### <a name="remarks"></a>Remarks  
 The member function does nothing. This member function is called after each call by `cache_freelist::deallocate` to operator `delete`. The argument `_Nx` is the number of memory blocks in the chunk deallocated by operator `delete`.  
  
##  <a name="full"></a>  max_none::full  
 Returns a value that specifies whether more memory blocks should be added to the free list.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Return Value  
 This member function always returns `true`.  
  
### <a name="remarks"></a>Remarks  
 This member function is called by `cache_freelist::deallocate`. If the call returns `true`, `deallocate` puts the memory block on the free list; if it returns false, `deallocate` calls operator `delete` to deallocate the block.  
  
##  <a name="released"></a>  max_none::released  
 Decrements the count of memory blocks on the free list.  
  
```
void released();
```  
  
### <a name="remarks"></a>Remarks  
 This member function does nothing. The `released` member function of the current max class is called by `cache_freelist::allocate` whenever it removes a memory block from the free list.  
  
##  <a name="saved"></a>  max_none::saved  
 Increments the count of memory blocks on the free list.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Remarks  
 This member function does nothing. It is called by `cache_freelist::deallocate` whenever it puts a memory block on the free list.  
  
## <a name="see-also"></a>See Also  
 [\<allocators>](../standard-library/allocators-header.md)




