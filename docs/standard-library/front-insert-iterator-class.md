---
title: front_insert_iterator Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::front_insert_iterator
- iterator/std::front_insert_iterator::container_type
- iterator/std::front_insert_iterator::reference
dev_langs:
- C++
helpviewer_keywords:
- std::front_insert_iterator [C++]
- std::front_insert_iterator [C++], container_type
- std::front_insert_iterator [C++], reference
ms.assetid: a9a9c075-136a-4419-928b-c4871afa033c
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: a4c0051b8117dbd46d3dab1ad5453f7aaabfbd49
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="frontinsertiterator-class"></a>front_insert_iterator Class
Describes an iterator adaptor that satisfies the requirements of an output iterator. It inserts, rather than overwrites, elements into the front of a sequence and thus provides semantics that are different from the overwrite semantics provided by the iterators of the C++ sequence containers. The `front_insert_iterator` class is templatized on the type of container.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Container>  
class front_insert_iterator;  
```  
  
#### <a name="parameters"></a>Parameters  
 `Container`  
 The type of container into the front of which elements are to be inserted by a `front_insert_iterator`.  
  
## <a name="remarks"></a>Remarks  
 The container must satisfy the requirements for a front insertion sequence where is it possible to insert elements at the beginning of the sequence in amortized constant time. The C++ Standard Library sequence containers defined by the [deque Class](../standard-library/deque-class.md) and [list Class](../standard-library/list-class.md) provide the needed `push_front` member function and satisfy these requirements. By contrast, sequence containers defined by the [vector Class](../standard-library/vector-class.md) do not satisfy these requirements and cannot be adapted to use with `front_insert_iterator`s. A `front_insert_iterator` must always be initialized with its container.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[front_insert_iterator](#front_insert_iterator)|Creates an iterator that can insert elements at the front of a specified container object.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#container_type)|A type that represents the container into which a front insertion is to be made.|  
|[reference](#reference)|A type that provides a reference to an element in a sequence controlled by the associated container.|  
  
### <a name="operators"></a>Operators  
  
|||  
|-|-|  
|[operator*](#op_star)|Dereferencing operator used to implement the output iterator expression * `i` = `x` for a front insertion.|  
|[operator++](#op_add_add)|Increments the `front_insert_iterator` to the next location into which a value may be stored.|  
|[operator=](#op_eq)|Assignment operator used to implement the output iterator expression * `i` = `x` for a front insertion.|  
  
## <a name="requirements"></a>Requirements  
 **Header**: \<iterator>  
  
 **Namespace:** std  
  
##  <a name="container_type"></a>  front_insert_iterator::container_type  
 A type that represents the container into which a front insertion is to be made.  
  
```  
typedef Container container_type;  
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **Container**.  
  
### <a name="example"></a>Example  
  
```cpp  
// front_insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> >::container_type L2 = L1;  
   front_inserter ( L2 ) = 20;  
   front_inserter ( L2 ) = 10;  
   front_inserter ( L2 ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++)  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 10 20 ).  
*\  
```  
  
##  <a name="front_insert_iterator"></a>  front_insert_iterator::front_insert_iterator  
 Creates an iterator that can insert elements at the front of a specified container object.  
  
```  
explicit front_insert_iterator(Container& _Cont);
```  
  
### <a name="parameters"></a>Parameters  
 `_Cont`  
 The container object into which the `front_insert_iterator` is to insert elements.  
  
### <a name="return-value"></a>Return Value  
 A `front_insert_iterator` for the parameter container object.  
  
### <a name="example"></a>Example  
  
```cpp  
// front_insert_iterator_front_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = -1 ; i < 9 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   front_inserter ( L ) = 20;  
  
   // Alternatively, one may use the template function  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="op_star"></a>  front_insert_iterator::operator*  
 Dereferences the insert iterator returning the element it addresses.  
  
```  
front_insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>Return Value  
 The member function returns the value of the element addressed.  
  
### <a name="remarks"></a>Remarks  
 Used to implement the output iterator expression **\*Iter** = **value**. If **Iter** is an iterator that addresses an element in a sequence, then **\*Iter** = **value** replaces that element with value and does not change the total number of elements in the sequence.  
  
### <a name="example"></a>Example  
  
```cpp  
// front_insert_iterator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for ( i = -1 ; i < 9 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator< list < int> > Iter(L);  
 *Iter = 20;  
  
   // Alternatively, you may use  
   front_inserter ( L ) = 30;  
  
   cout << "After the front insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( -2 0 2 4 6 8 10 12 14 16 ).  
After the front insertions, the list L is:  
 ( 30 20 -2 0 2 4 6 8 10 12 14 16 ).  
*\  
```  
  
##  <a name="op_add_add"></a>  front_insert_iterator::operator++  
 Increments the `back_insert_iterator` to the next location into which a value may be stored.  
  
```  
front_insert_iterator<Container>& operator++();

front_insert_iterator<Container> operator++(int);
```  
  
### <a name="return-value"></a>Return Value  
 A `front_insert_iterator` addressing the next location into which a value may be stored.  
  
### <a name="remarks"></a>Remarks  
 Both preincrementation and postincrementation operators return the same result.  
  
### <a name="example"></a>Example  
  
```cpp  
// front_insert_iterator_op_incre.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="op_eq"></a>  front_insert_iterator::operator=  
 Appends (pushes) a value onto the front of the container.  
  
```  
front_insert_iterator<Container>& operator=(typename Container::const_reference val);

front_insert_iterator<Container>& operator=(typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>Parameters  
 `val`  
 The value to be assigned to the container.  
  
### <a name="return-value"></a>Return Value  
 A reference to the last element inserted at the front of the container.  
  
### <a name="remarks"></a>Remarks  
 The first member operator evaluates `container.push_front( val)`, then returns `*this`.  
  
 The second member operator evaluates  
  
 `container->push_front((typename Container::value_type&&) val)`,  
  
 then returns `*this`.  
  
### <a name="example"></a>Example  
  
```cpp  
// front_insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   front_insert_iterator<list<int> > iter ( L1 );  
 *iter = 10;  
   iter++;  
 *iter = 20;  
   iter++;  
 *iter = 30;  
   iter++;  
  
   list <int>::iterator vIter;  
   cout << "The list L1 is: ( ";  
   for ( vIter = L1.begin ( ) ; vIter != L1.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L1 is: ( 30 20 10 ).  
*\  
```  
  
##  <a name="reference"></a>  front_insert_iterator::reference  
 A type that provides a reference to an element in a sequence controlled by the associated container.  
  
```  
typedef typename Container::reference reference;  
```  
  
### <a name="example"></a>Example  
  
```cpp  
// front_insert_iterator_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   front_insert_iterator<list<int> > fiivIter( L );  
 *fiivIter = 10;  
 *fiivIter = 20;  
 *fiivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++)  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   front_insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 30 20 10 ).  
The first element in the list L is: 30.  
*\  
```  
  
## <a name="see-also"></a>See Also  
 [\<iterator>](../standard-library/iterator.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standard Library Reference](../standard-library/cpp-standard-library-reference.md)


