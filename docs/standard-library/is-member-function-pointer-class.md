---
title: is_member_function_pointer Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_member_function_pointer
dev_langs:
- C++
helpviewer_keywords:
- is_member_function_pointer class
- is_member_function_pointer
ms.assetid: 02e372c4-2714-40f2-b376-2e10ca91c8ed
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
ms.openlocfilehash: 0d3b940c339247d1373c56d85759d5aa85949bdb
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ismemberfunctionpointer-class"></a>is_member_function_pointer Class
Tests if type is a pointer to member function.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct is_member_function_pointer;  
```  
  
#### <a name="parameters"></a>Parameters  
 `Ty`  
 The type to query.  
  
## <a name="remarks"></a>Remarks  
 An instance of the type predicate holds true if the type `Ty` is a pointer to member function or a `cv-qualified` pointer to member function, otherwise it holds false.  
  
## <a name="example"></a>Example  
  
```cpp  
// std__type_traits__is_member_function_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_member_function_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_function_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_function_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_member_function_pointer<trivial *> == false  
is_member_function_pointer<int trivial::*> == false  
is_member_function_pointer<int (functional::*)()> == true  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_member_pointer Class](../standard-library/is-member-pointer-class.md)

