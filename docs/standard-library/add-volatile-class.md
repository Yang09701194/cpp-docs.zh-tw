---
title: add_volatile Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 21
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
ms.openlocfilehash: 7ffd6be369667a5141f269ca4c42a1093a8e8723
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="addvolatile-class"></a>add_volatile Class
Makes a volatile type from the specified type.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct add_volatile;  
 
template <class T>
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
### <a name="parameters"></a>Parameters  
*T*  
The type to modify.  
  
## <a name="remarks"></a>Remarks  
An instance of `add_volatile<T>` has a member typedef `type` that is *T* if *T* is a reference, a function, or a volatile-qualified type, otherwise `volatile` *T*. The alias `add_volatile_t` is a shortcut to access the member typedef `type`. 
  
## <a name="example"></a>Example  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
} 
```  
  
```Output  
add_volatile<int> == int  
```  
  
## <a name="requirements"></a>Requirements  

**Header:** \<type_traits>  
  
**Namespace:** std  
  
## <a name="see-also"></a>See Also  
[<type_traits>](../standard-library/type-traits.md)   
[remove_volatile Class](../standard-library/remove-volatile-class.md)

