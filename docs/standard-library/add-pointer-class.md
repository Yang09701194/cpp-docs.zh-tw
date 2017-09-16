---
title: add_pointer Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
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
ms.openlocfilehash: 5b7f0fa84b8a99b5e2225dfdf4028807f2d89eaa
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="addpointer-class"></a>add_pointer Class
Makes a pointer-to-type from a specified type.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
struct add_pointer;  
 
template <class T>
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### <a name="parameters"></a>Parameters  
*T*  
The type to modify.  
  
## <a name="remarks"></a>Remarks  
The member typedef `type` names the same type as `remove_reference<T>::type*`. The alias `add_pointer_t` is a shortcut to access the member typedef `type`.  
  
Because it is invalid to make a pointer from a reference, `add_pointer` removes the reference, if any, from the specified type before it makes a pointer-to-type. Consequently, you can use a type with `add_pointer` without being concerned about whether the type is a reference.  
  
## <a name="example"></a>Example  
The following example demonstrates that `add_pointer` of a type is the same as a pointer to that type.  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_pointer_t<int> == int *  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_pointer Class](../standard-library/remove-pointer-class.md)

