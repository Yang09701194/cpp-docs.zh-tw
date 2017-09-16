---
title: '&lt;memory&gt; operators | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
dev_langs:
- C++
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 9a8504cadcd584e423a1050c7fa02b935a1fa0e9
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltmemorygt-operators"></a>&lt;memory&gt; operators
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|  
|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 Tests for inequality between objects.  
  
```  
template <class Type, class Other>  
bool operator!=(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>  
bool operator!=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator!=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `left`  
 One of the objects to be tested for inequality.  
  
 `right`  
 One of the objects to be tested for inequality.  
  
 `Ty1`  
 The type controlled by the left shared pointer.  
  
 `Ty2`  
 The type controlled by the right shared pointer.  
  
### <a name="return-value"></a>Return Value  
 **true** if the objects are not equal; **false** if objects are equal.  
  
### <a name="remarks"></a>Remarks  
 The first template operator returns false. (All default allocators are equal.)  
  
 The second and third template operators return `!(left == right)`.  
  
### <a name="example"></a>Example  
  
```cpp  
// memory_op_me.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <char>:: allocator_type v1Alloc;  
  
   if ( Alloc != v1Alloc )  
      cout << "The allocator objects Alloc & v1Alloc not are equal."  
           << endl;  
   else  
      cout << "The allocator objects Alloc & v1Alloc are equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects Alloc & v1Alloc are equal.  
```  
  
### <a name="example"></a>Example  
  
```cpp  
// std__memory__operator_ne.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 != sp0 == " << std::boolalpha   
        << (sp0 != sp0) << std::endl;   
    std::cout << "sp0 != sp1 == " << std::boolalpha   
        << (sp0 != sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 != sp0 == false  
sp0 != sp1 == true  
```  
  
##  <a name="op_eq_eq"></a>  operator==  
 Tests for equality between objects.  
  
```  
template <class Type, class Other>  
bool operator==(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator==(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>  
bool operator==(
    const shared_ptr<Ty1>& left;,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `left`  
 One of the objects to be tested for equality.  
  
 `right`  
 One of the objects to be tested for equality.  
  
 `Ty1`  
 The type controlled by the left shared pointer.  
  
 `Ty2`  
 The type controlled by the right shared pointer.  
  
### <a name="return-value"></a>Return Value  
 `true` if the objects are equal, `false` if objects are not equal.  
  
### <a name="remarks"></a>Remarks  
 The first template operator returns true. (All default allocators are equal.)  
  
 The second and third template operators return ` left.get() ==  right.get()`.  
  
### <a name="example"></a>Example  
  
```cpp  
// memory_op_eq.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<char> Alloc;  
   vector <int>:: allocator_type v1Alloc;  
  
   allocator<char> cAlloc(Alloc);   
   allocator<int> cv1Alloc(v1Alloc);  
  
   if ( cv1Alloc == v1Alloc )  
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."  
           << endl;  
  
   if ( cAlloc == Alloc )  
      cout << "The allocator objects cAlloc & Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cAlloc & Alloc are not equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects cv1Alloc & v1Alloc are equal.  
The allocator objects cAlloc & Alloc are equal.  
```  
  
### <a name="example"></a>Example  
  
```cpp  
// std__memory__operator_eq.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 == sp0 == " << std::boolalpha   
        << (sp0 == sp0) << std::endl;   
    std::cout << "sp0 == sp1 == " << std::boolalpha   
        << (sp0 == sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == sp0 == true  
sp0 == sp1 == false  
```  
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
 Tests for one object being greater than or equal to a second object.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator>=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>  
bool operator>=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `left`  
 One of the objects to be compared.  
  
 `right`  
 One of the objects to be compared.  
  
 `Ty1`  
 The type controlled by the left shared pointer.  
  
 `Ty2`  
 The type controlled by the right shared pointer.  
  
### <a name="remarks"></a>Remarks  
 The template operators return `left.get() >= right.get()`.  
  
##  <a name="op_lt"></a>  operator&lt;  
 Tests for one object being less than a second object.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `left`  
 One of the objects to be compared.  
  
 `right`  
 One of the objects to be compared.  
  
 `Ty1`  
 The type controlled by the left pointer.  
  
 `Ty2`  
 The type controlled by the right pointer.  
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
 Tests for one object being less than or equal to a second object.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `left`  
 One of the objects to be compared.  
  
 `right`  
 One of the objects to be compared.  
  
 `Ty1`  
 The type controlled by the left shared pointer.  
  
 `Ty2`  
 The type controlled by the right shared pointer.  
  
### <a name="remarks"></a>Remarks  
 The template operators return `left.get() <= right.get()`  
  
##  <a name="op_gt"></a>  operator&gt;  
 Tests for one object being greater than a second object.  
  
```  
template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator>(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>  
bool operator>(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `left`  
 One of the objects to be compared.  
  
 `right`  
 One of the objects to be compared.  
  
 `Ty1`  
 The type controlled by the left shared pointer.  
  
 `Ty2`  
 The type controlled by the right shared pointer.  
  
##  <a name="op_lt_lt"></a>  operator&lt;&lt;  
Writes the shared pointer to the stream.  
  
```  
template <class Elem, class Tr, class Ty>  
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,  
    shared_ptr<Ty>& sp);
```  
  
### <a name="parameters"></a>Parameters  
 `Elem`  
 The type of the stream element.  
  
 `Tr`  
 The type the stream element traits.  
  
 `Ty`  
 The type controlled by the shared pointer.  
  
 `out`  
 The output stream.  
  
 `sp`  
 The shared pointer.  
  
### <a name="remarks"></a>Remarks  
 The template function returns `out << sp.get()`.  
  
### <a name="example"></a>Example  
  
```cpp  
// std__memory__operator_sl.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(5));   
  
    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == 3f3040 (varies)  
```  
  
## <a name="see-also"></a>See Also  
 [\<memory>](../standard-library/memory.md)


