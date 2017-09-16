---
title: is_trivially_constructible Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
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
ms.openlocfilehash: fe756def468770270140ebc7cb6c9a91f2b926b2
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible Class
Tests whether a type is trivially constructible when the specified argument types are used.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class... Args>  
struct is_trivially_constructible;
```  
  
#### <a name="parameters"></a>Parameters  
 `T`  
 The type to query.  
  
 `Args`  
 The argument types to match in a constructor of `T`.  
  
## <a name="remarks"></a>Remarks  
 An instance of the type predicate holds true if the type `T` is trivially constructible by using the argument types in `Args`, otherwise it holds false. Type `T` is trivially constructible if the variable definition `T t(std::declval<Args>()...);` is well-formed and is known to call no non-trivial operations. Both `T` and all the types in `Args` must be complete types, `void`, or arrays of unknown bound.  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [<type_traits>](../standard-library/type-traits.md)




