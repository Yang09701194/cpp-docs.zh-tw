---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_map>", "std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: c3807ad83dc756ce62acd3e4f3fb5168e6d2d624
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  This header is obsolete. The alternative is [<unordered_map>](../standard-library/unordered-map.md).  
  
 Defines the container template classes hash_map and hash_multimap and their supporting templates.  
  
 In Visual C++ .NET 2003, members of the <hash_map> and <hash_set> header files are no longer in the std namespace, but rather have been moved into the stdext namespace. See [stdext Namespace](../standard-library/stdext-namespace.md) for more information.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>Operators  
  
|Hash_map version|Hash_multimap version|Description|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](../standard-library/hash-map-operators.md#op_neq)|`operator!= (hash_multimap)`|Tests if the hash_map or hash_multimap object on the left side of the operator is not equal to the hash_map or hash_multimap object on the right side.|  
|[operator== (hash_map)](../standard-library/hash-map-operators.md#op_eq_eq)|`operator== (hash_multimap)`|Tests if the hash_map or hash_multimap object on the left side of the operator is equal to the hash_map or hash_multimap object on the right side.|  
  
### <a name="specialized-template-functions"></a>Specialized Template Functions  
  
|Hash_map version|Hash_multimap version|Description|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](../standard-library/hash-map-class.md#swap)|[swap (hash_multimap)](../standard-library/hash-multimap-class.md#swap)|Exchanges the elements of two hash_maps or hash_multimaps.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[hash_compare Class](../standard-library/hash-compare-class.md)|Describes an object that can be used by any of the hash associative containers — hash_map, hash_multimap, hash_set, or hash_multiset — as a default **Traits** parameter object to order and hash the elements they contain.|  
|[value_compare Class](../standard-library/value-compare-class.md)|Provides a function object that can compare the elements of a hash_map by comparing the values of their keys to determine their relative order in the hash_map.|  
|[hash_map Class](../standard-library/hash-map-class.md)|Used for the storage and fast retrieval of data from a collection in which each element is a pair that has a sort key whose value is unique and an associated data value.|  
|[hash_multimap Class](../standard-library/hash-multimap-class.md)|Used for the storage and fast retrieval of data from a collection in which each element is a pair that has a sort key whose value need not be unique and an associated data value.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<hash_map>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>See Also  
 [Header Files Reference](../standard-library/cpp-standard-library-header-files.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standard Library Reference](../standard-library/cpp-standard-library-reference.md)




