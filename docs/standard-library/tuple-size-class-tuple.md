---
title: tuple_size Class; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple_size", "std::tuple_size", "utility/std::tuple_size
dev_langs:
- C++
helpviewer_keywords:
- ', '
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
caps.latest.revision: 23
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
ms.openlocfilehash: 15bc0b29c4775438ee93b899c061aa539f5c1546
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="tuplesize-class"></a>tuple_size Class;
Reports the number of elements that a `tuple` contains.  
  
## <a name="syntax"></a>Syntax  
  
```  
// TEMPLATE STRUCT tuple_size  
template <class Tuple>  
   struct tuple_size;  
  
// number of elements in array  
template <class Elem, size_t Size>  
   struct tuple_size<array<Elem, Size>>  
      : integral_constant<size_t, Size>; 
  
// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>> 
      : integral_constant<size_t, 2>

// size of tuple  
template <class... Types>  
   struct tuple_size<tuple<Types...>>  
      : integral_constant<size_t, sizeof...(Types)>;  
  
// size of const tuple  
template <class Tuple>  
   struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template <class Tuple>  
   struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template <class Tuple>  
   struct tuple_size<const volatile Tuple>;   
```  
  
#### <a name="parameters"></a>Parameters  
*Tuple*  
The type of the tuple. 
  
*Elem*  
The type of the array elements. 
  
*Size*  
The size of the array. 
  
*T1*  
The type of the first member of the pair. 
  
*T2*  
The type of the second member of the pair. 
  
*Types*  
The types of the tuple elements. 
  
  
## <a name="remarks"></a>Remarks  
The template class has a member `value` that is an integral constant expression whose value is the extent of the tuple type `Tuple`.  
  
The template specialization for arrays has a member `value` that is an integral constant expression whose value is `Size`, which is the size of the array.  
  
The template specialization for pair has a member `value` that is an integral constant expression whose value is 2.  
  
## <a name="example"></a>Example  
  
```cpp  
#include <tuple>   
#include <iostream>  
  
using namespace std;  
  
typedef tuple<int, double, int, double> MyTuple;  
int main()  
{  
    MyTuple c0(0, 1.5, 2, 3.7);  
  
    // display contents " 0 1 2 3"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0);  
    cout << " " << get<2>(c0);  
    cout << " " << get<3>(c0) << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyTuple>::value << endl;  
}  
```  
  
```Output  
 0 1.5 2 3.7  
```  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<tuple>  
 **Header:** \<array> (for array specialization)  
 **Header:** \<utility> (for pair specialization)  
  
 **Namespace:** std  
  
## <a name="see-also"></a>See Also  
 [\<tuple>](../standard-library/tuple.md)   
 [tuple](../standard-library/tuple-class.md)  
 [tuple_element Class](../standard-library/tuple-element-class-tuple.md)

