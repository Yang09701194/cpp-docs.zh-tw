---
title: max_variable_size Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
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
ms.openlocfilehash: 3ba2450e4079307d26402dd56532686f687ab3f4
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="maxvariablesize-class"></a>max_variable_size Class
Describes a [max class](../standard-library/allocators-header.md) object that limits a [freelist](../standard-library/freelist-class.md) object to a maximum length that is roughly proportional to the number of allocated memory blocks.  
  
## <a name="syntax"></a>Syntax  
  
```
class max_variable_size
```  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[max_variable_size](#max_variable_size)|Constructs an object of type `max_variable_size`.|  
  
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
  
##  <a name="allocated"></a>  max_variable_size::allocated  
 Increments the count of allocated memory blocks.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`_Nx`|The increment value.|  
  
### <a name="remarks"></a>Remarks  
 This member function adds `_Nx` to the stored value `_Nallocs`. This member function is called after each successful call by `cache_freelist::allocate` to operator `new`. The argument `_Nx` is the number of memory blocks in the chunk allocated by operator `new`.  
  
##  <a name="deallocated"></a>  max_variable_size::deallocated  
 Decrements the count of allocated memory blocks.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`_Nx`|The increment value.|  
  
### <a name="remarks"></a>Remarks  
 The member function subtracts `_Nx` from the stored value `_Nallocs`. This member function is called after each call by `cache_freelist::deallocate` to operator `delete`. The argument `_Nx` is the number of memory blocks in the chunk deallocated by operator `delete`.  
  
##  <a name="full"></a>  max_variable_size::full  
 Returns a value that specifies whether more memory blocks should be added to the free list.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Return Value  
 `true` if `_Nallocs / 16 + 16 <= _Nblocks`.  
  
### <a name="remarks"></a>Remarks  
 This member function is called by `cache_freelist::deallocate`. If the call returns `true`, `deallocate` puts the memory block on the free list; if it returns false, `deallocate` calls operator `delete` to deallocate the block.  
  
##  <a name="max_variable_size"></a>  max_variable_size::max_variable_size  
 Constructs an object of type `max_variable_size`.  
  
```
max_variable_size();
```  
  
### <a name="remarks"></a>Remarks  
 The constructor initializes the stored values `_Nblocks` and `_Nallocs` to zero.  
  
##  <a name="released"></a>  max_variable_size::released  
 Decrements the count of memory blocks on the free list.  
  
```
void released();
```  
  
### <a name="remarks"></a>Remarks  
 This member function decrements the stored value `_Nblocks`. The `released` member function of the current max class is called by `cache_freelist::allocate` whenever it removes a memory block from the free list.  
  
##  <a name="saved"></a>  max_variable_size::saved  
 Increments the count of memory blocks on the free list.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Remarks  
 This member function increments the stored value `_Nblocks`. This member function is called by `cache_freelist::deallocate` whenever it puts a memory block on the free list.  
  
## <a name="see-also"></a>See Also  
 [\<allocators>](../standard-library/allocators-header.md)




