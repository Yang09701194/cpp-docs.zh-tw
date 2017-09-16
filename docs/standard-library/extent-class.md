---
title: extent Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::extent
dev_langs:
- C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: 20
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
ms.openlocfilehash: 2c7650f705b47075bd03fe5b3d04c749441c28a0
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="extent-class"></a>extent Class
Gets an array dimension.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty, unsigned I = 0>  
struct extent;  
```  
  
#### <a name="parameters"></a>Parameters  
 `Ty`  
 The type to query.  
  
 `I`  
 The array bound to query.  
  
## <a name="remarks"></a>Remarks  
 If `Ty` is an array type that has at least `I` dimensions, the type query holds the number of elements in the dimension specified by `I`. If `Ty` is not an array type or its rank is less than `I`, or if `I` is zero and `Ty` is of type "array of unknown bound of `U`", the type query holds the value 0.  
  
## <a name="example"></a>Example  
  
```cpp  
// std__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
extent 0 == 5  
extent 1 == 10  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_all_extents Class](../standard-library/remove-all-extents-class.md)   
 [remove_extent Class](../standard-library/remove-extent-class.md)

