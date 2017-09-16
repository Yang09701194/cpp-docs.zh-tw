---
title: '&lt;allocators&gt; operators | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: ef4366ab1d13e96a432de4929f86ef27f86e60e7
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; operators
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 Tests for inequality between allocator objects of a specified class.  
  
```
template <class Type, class Sync>  
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`left`|One of the allocator objects to be tested for inequality.|  
|`right`|One of the allocator objects to be tested for inequality.|  
  
### <a name="return-value"></a>Return Value  
 **true** if the allocator objects are not equal; **false** if allocator objects are equal.  
  
### <a name="remarks"></a>Remarks  
 The template operator returns `!(left == right)`.  
  
##  <a name="op_eq_eq"></a>  operator==  
 Tests for equality between allocator objects of a specified class.  
  
```
template <class Type, class Sync>  
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|`left`|One of the allocator objects to be tested for equality.|  
|`right`|One of the allocator objects to be tested for equality.|  
  
### <a name="return-value"></a>Return Value  
 **true** if the allocator objects are equal; **false** if allocator objects are not equal.  
  
### <a name="remarks"></a>Remarks  
 This template operator returns `left.equals(right)`.  
  
## <a name="see-also"></a>See Also  
 [\<allocators>](../standard-library/allocators-header.md)




