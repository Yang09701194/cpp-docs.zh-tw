---
title: '&lt;array&gt; functions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array/std::array::get
- array/std::get
- array/std::swap
dev_langs:
- C++
ms.assetid: e0700a33-a833-4655-8735-16e71175efc8
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::array [C++], get
- std::get [C++]
- std::swap [C++]
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: d7bb16b490d20934a263147c0d6e28694e006552
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltarraygt-functions"></a>&lt;array&gt; functions
The \<array> header includes two non-member functions, `get` and `swap`, that operate on `array` objects.  
  
|||  
|-|-|  
|[get](#get)|[swap](#swap)|  
  
##  <a name="get"></a>  get  
Returns a reference to the specified element of the array.  
  
```  
template <int Index, class T, size_t N>  
constexpr T& get(array<T, N>& arr) noexcept;  
 
template <int Index, class T, size_t N>  
constexpr const T& get(const array<T, N>& arr) noexcept;  
 
template <int Index, class T, size_t N>  
constexpr T&& get(array<T, N>&& arr) noexcept;  
```  
  
### <a name="parameters"></a>Parameters  
 `Index`  
 The element offset.  
  
 `T`  
 The type of an element.  
  
 `N`  
 The number of elements in the array.  
  
 `arr`  
 The array to select from.  
  
### <a name="example"></a>Example  
  
```cpp  
#include <array>   
#include <iostream>   
  
using namespace std;  
  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    // display contents " 0 1 2 3"   
    for (const auto& e : c0)  
    {  
        cout << " " << e;  
    }  
    cout << endl;  
  
    // display odd elements " 1 3"   
    cout << " " << get<1>(c0);  
    cout << " " << get<3>(c0) << endl;  
}  
```  
  
```Output  
0 1 2 3  
1 3  
```  
  
##  <a name="swap"></a>  swap  
A non-member template specialization of `std::swap` that swaps two `array` objects.  
  
```  
template <class Ty, std::size_t N>  
void swap(array<Ty, N>& left, array<Ty, N>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `Ty`  
 The type of an element.  
  
 `N`  
 The size of the array.  
  
 `left`  
 The first array to swap.  
  
 `right`  
 The second array to swap.  
  
### <a name="remarks"></a>Remarks  
 The template function executes `left.swap(right)`.  
  
### <a name="example"></a>Example  
  
```cpp  
// std__array__swap.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = { 4, 5, 6, 7 };
    c0.swap(c1);

    // display swapped contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    swap(c0, c1);

    // display swapped contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
}
```  
  
```Output  
0 1 2 3  
4 5 6 7  
0 1 2 3  
```  
  
## <a name="see-also"></a>See Also  
 [\<array>](../standard-library/array.md)


