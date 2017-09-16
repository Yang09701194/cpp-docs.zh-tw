---
title: ostream_iterator Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::ostream_iterator
- iterator/std::ostream_iterator::char_type
- iterator/std::ostream_iterator::ostream_type
- iterator/std::ostream_iterator::traits_type
dev_langs:
- C++
helpviewer_keywords:
- std::ostream_iterator [C++]
- std::ostream_iterator [C++], char_type
- std::ostream_iterator [C++], ostream_type
- std::ostream_iterator [C++], traits_type
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
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
ms.openlocfilehash: 0efff60ddb49fdfef0354a0c32b4b1a90f345883
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ostreamiterator-class"></a>ostream_iterator Class
The template class ostream_iterator describes an output iterator object that writes successive elements onto the output stream with the extraction **operator <<**.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Type class CharType = char class Traits = char_traits <CharType>>  
class ostream_iterator
```  
  
#### <a name="parameters"></a>Parameters  
 *Type*  
 The type of object to be inserted into the output stream.  
  
 `CharType`  
 The type that represents the character type for the `ostream_iterator`. This argument is optional and the default value is `char`.  
  
 `Traits`  
 The type that represents the character type for the `ostream_iterator`. This argument is optional and the default value is `char_traits`\< *CharType>.*  
  
 The ostream_iterator class must satisfy the requirements for an output iterator. Algorithms can be written directly to output streams using an `ostream_iterator`.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[ostream_iterator](#ostream_iterator)|Constructs an `ostream_iterator` that is initialized and delimited to write to the output stream.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|A type that provides for the character type of the `ostream_iterator`.|  
|[ostream_type](#ostream_type)|A type that provides for the stream type of the `ostream_iterator`.|  
|[traits_type](#traits_type)|A type that provides for the character traits type of the `ostream_iterator`.|  
  
### <a name="operators"></a>Operators  
  
|||  
|-|-|  
|[operator*](#op_star)|Dereferencing operator used to implement the output iterator expression * `i` = `x`.|  
|[operator++](#op_add_add)|A nonfunctional increment operator that returns an `ostream_iterator` to the same object it addressed before the operation was called.|  
|[operator=](#op_eq)|Assignment operator used to implement the output iterator expression * `i` = `x` for writing to an output stream.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  ostream_iterator::char_type  
 A type that provides for the character type of the iterator.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **CharType**.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostream_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostream_iterator<int>::char_type CHT1;  
   typedef ostream_iterator<int>::traits_type CHTR1;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter:  
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream:  
   cout << "The integers written to the output stream\n"  
        << "by intOut are:" << endl;  
 *intOut = 10;  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
The integers written to the output stream  
by intOut are:  
10  
20  
30  
*\  
```  
  
##  <a name="op_star"></a>  ostream_iterator::operator*  
 Dereferencing operator used to implement the output iterator expression \* *ii* = *x*.  
  
```
ostream_iterator<Type, CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>Return Value  
 A reference to the `ostream_iterator`.  
  
### <a name="remarks"></a>Remarks  
 The requirements for an output iterator that the `ostream_iterator` must satisfy require only the expression \* *ii* = *t* be valid and says nothing about the **operator** or the `operator=` on their own. The member operator in this implementation returns **\*this**.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostream_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="op_add_add"></a>  ostream_iterator::operator++  
 A nonfunctional increment operator that returns an `ostream_iterator` to the same object it addressed before the operation was called.  
  
```
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```  
  
### <a name="return-value"></a>Return Value  
 A reference to the `ostream_iterator`.  
  
### <a name="remarks"></a>Remarks  
 These member operators both return **\*this**.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostream_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="op_eq"></a>  ostream_iterator::operator=  
 Assignment operator used to implement the output_iterator expression * `i` = `x` for writing to an output stream.  
  
```
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```  
  
### <a name="parameters"></a>Parameters  
 `val`  
 The value of the object of type `Type` to be inserted into the output stream.  
  
### <a name="return-value"></a>Return Value  
 The operator inserts `val` into the output stream associated with the object, followed by the delimiter specified in the [ostream_iterator constructor](#ostream_iterator) (if any), and then returns a reference to the `ostream_iterator`.  
  
### <a name="remarks"></a>Remarks  
 The requirements for an output iterator that the `ostream_iterator` must satisfy require only the expression * `ii` = `t` be valid and says nothing about the operator or the operator= on their own. This member operator returns `*this`.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostream_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="ostream_iterator"></a>  ostream_iterator::ostream_iterator  
 Constructs an `ostream_iterator` that is initialized and delimited to write to the output stream.  
  
```
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```  
  
### <a name="parameters"></a>Parameters  
 `_Ostr`  
 The output stream of type [ostream_iterator::ostream_type](#ostream_type) to be iterated over.  
  
 `_Delimiter`  
 The delimiter that is inserted into the output stream between values.  
  
### <a name="remarks"></a>Remarks  
 The first constructor initializes the output stream pointer with `&_Ostr`. The delimiter string pointer designates an empty string.  
  
 The second constructor initializes the output stream pointer with `&_Ostr` and the delimiter string pointer with `_Delimiter`.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostream_iterator_ostream_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   ostream_iterator<int> intOut ( cout , "\n" );  
 *intOut = 10;  
   intOut++;  
 *intOut = 20;  
   intOut++;  
  
   int i;  
   vector<int> vec;  
   for ( i = 1 ; i < 7 ; ++i )  
   {  
      vec.push_back (  i );  
   }  
  
   // Write elements to standard output stream  
   cout << "Elements output without delimiter: ";  
   copy ( vec.begin ( ), vec.end ( ),  
          ostream_iterator<int> ( cout ) );  
   cout << endl;  
  
   // Write elements with delimiter " : " to output stream  
   cout << "Elements output with delimiter: ";  
   copy ( vec.begin ( ), vec.end ( ),  
          ostream_iterator<int> ( cout, " : " ) );  
   cout << endl;  
}  
\* Output:   
10  
20  
Elements output without delimiter: 123456  
Elements output with delimiter: 1 : 2 : 3 : 4 : 5 : 6 :   
*\  
```  
  
##  <a name="ostream_type"></a>  ostream_iterator::ostream_type  
 A type that provides for the stream type of the iterator.  
  
```
typedef basic_ostream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`>, a stream class of the iostream hierarchy that defines objects that can be used for writing.  
  
### <a name="example"></a>Example  
  See [ostream_iterator](#ostream_iterator) for an example of how to declare and use `ostream_type`.  
  
##  <a name="traits_type"></a>  ostream_iterator::traits_type  
 A type that provides for the character traits type of the iterator.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **Traits**.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostream_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The following not OK, but are just the default values:  
   typedef ostream_iterator<int>::char_type CHT1;  
   typedef ostream_iterator<int>::traits_type CHTR1;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter:  
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream:  
   cout << "The integers written to output stream\n"  
        << "by intOut are:" << endl;  
 *intOut = 1;  
 *intOut = 10;  
 *intOut = 100;  
}  
\* Output:   
The integers written to output stream  
by intOut are:  
1  
10  
100  
*\  
```  
  
## <a name="see-also"></a>See Also  
 [\<iterator>](../standard-library/iterator.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standard Library Reference](../standard-library/cpp-standard-library-reference.md)




