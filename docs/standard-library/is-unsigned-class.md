---
title: is_unsigned Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_unsigned
dev_langs:
- C++
helpviewer_keywords:
- is_unsigned class
- is_unsigned
ms.assetid: ba5bec3d-796b-4e54-8595-a3941ec6a8dc
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
ms.openlocfilehash: a0c2172cee531ce403836e3b6698ee0dfc30621f
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="isunsigned-class"></a>is_unsigned Class
Tests if type is unsigned integer.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct is_unsigned;  
```  
  
#### <a name="parameters"></a>Parameters  
 `Ty`  
 The type to query.  
  
## <a name="remarks"></a>Remarks  
 An instance of the type predicate holds true if the type `Ty` is an unsigned integral type or a `cv-qualified` unsigned integral type, otherwise it holds false.  
  
## <a name="example"></a>Example  
  
```cpp  
// std__type_traits__is_unsigned.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_unsigned<trivial> == " << std::boolalpha   
        << std::is_unsigned<trivial>::value << std::endl;   
    std::cout << "is_unsigned<int> == " << std::boolalpha   
        << std::is_unsigned<int>::value << std::endl;   
    std::cout << "is_unsigned<unsigned int> == " << std::boolalpha   
        << std::is_unsigned<unsigned int>::value << std::endl;   
    std::cout << "is_unsigned<float> == " << std::boolalpha   
        << std::is_unsigned<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_unsigned<trivial> == false  
is_unsigned<int> == false  
is_unsigned<unsigned int> == true  
is_unsigned<float> == false  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_signed Class](../standard-library/is-signed-class.md)

