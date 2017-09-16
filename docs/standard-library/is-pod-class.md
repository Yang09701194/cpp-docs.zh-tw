---
title: is_pod Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
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
ms.openlocfilehash: ecbad6c19819f6d99ec7cfd3d34d61e1e0201569
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ispod-class"></a>is_pod Class
Tests if type is POD.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
struct is_pod;
```  
  
#### <a name="parameters"></a>Parameters  
*T*  
The type to query.  
  
## <a name="remarks"></a>Remarks  
`is_pod<T>::value` is `true` if the type *T* is Plain Old Data (POD). Otherwise it is `false`.  
  
Arithmetic types, enumeration types, pointer types, and pointer to member types are POD.  
  
A cv-qualified version of a POD type is itself a POD type.  
  
An array of POD is itself POD.  
  
A struct or union, all of whose non-static data members are POD, is itself POD if it has:  
  
-   No user-declared constructors.  
  
-   No private or protected non-static data members.  
  
-   No base classes.  
  
-   No virtual functions.  
  
-   No non-static data members of reference type.  
  
-   No user-defined copy assignment operator.  
  
-   No user-defined destructor.  
  
Therefore, you can recursively build POD structs and arrays that contain POD structs and arrays.  
  
## <a name="example"></a>Example  
  
```cpp  
// std__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial {   
    int val;   
};   
  
struct throws {   
    throws() {}  // User-declared ctor, so not POD
  
    int val;   
};   
  
int main() {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
is_pod<trivial> == true  
is_pod<int> == true  
is_pod<throws> == false  
```  
  
## <a name="requirements"></a>Requirements  
**Header:** \<type_traits>  
  
**Namespace:** std  
  
## <a name="see-also"></a>See Also  
[<type_traits>](../standard-library/type-traits.md)




