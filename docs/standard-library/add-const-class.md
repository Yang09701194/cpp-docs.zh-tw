---
title: add_const Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_const
dev_langs:
- C++
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
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
ms.openlocfilehash: 7865a718b4fa0ed95971ec091d5cfcd1b18a92ac
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="addconst-class"></a>add_const Class
Makes const type from type.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct add_const;
```  
  
#### <a name="parameters"></a>Parameters  
 `Ty`  
 The type to modify.  
  
## <a name="remarks"></a>Remarks  
 An instance of the type modifier holds a modified-type that is `Ty` if `Ty` is a reference, a function, or a const-qualified type, otherwise `const Ty`.  
  
## <a name="example"></a>Example  
  
```cpp  
// std__type_traits__add_const.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_const<int>::type *p = (const int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_const<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_const<int> == int  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_const Class](../standard-library/remove-const-class.md)

