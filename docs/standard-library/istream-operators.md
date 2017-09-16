---
title: '&lt;istream&gt; operators | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::operator&gt;&gt;
dev_langs:
- C++
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 5d026c375025b169d5db8445cbb52c0c917b2d8d
ms.openlocfilehash: 99f20cdf8aa0a8fd19bac697fdac1bb2f642bf8e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; operators
 
##  <a name="op_gt_gt"></a>  operator&gt;&gt;  
 Extracts characters and strings from the stream.  
  
```  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem* str);

template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char& Ch);

template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
### <a name="parameters"></a>Parameters  
 `Ch`  
 A character.  
  
 `Istr`  
 A stream.  
  
 `str`  
 A string.  
  
 `val`  
 A type.  
  
### <a name="return-value"></a>Return Value  
 The stream  
  
### <a name="remarks"></a>Remarks  
 The `basic_istream` class also defines several extraction operators. For more information, see [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).  
  
 The template function:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```  
  
 extracts up to *N* - 1 elements and stores them in the array starting at _ *Str*. If `Istr`. [width](../standard-library/ios-base-class.md#width) is greater than zero, *N* is `Istr`. **width**; otherwise, it is the size of the largest array of **Elem** that can be declared. The function always stores the value **Elem()** after any extracted elements it stores. Extraction stops early on end of file, on a character with value **Elem**(0) (which is not extracted), or on any element (which is not extracted) that would be discarded by [ws](../standard-library/istream-functions.md#ws). If the function extracts no elements, it calls `Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). In any case, it calls `Istr`. **width**(0) and returns `Istr`.  
  
 **Security Note** The null-terminated string being extracted from the input stream must not exceed the size of the destination buffer `str`. For more information, see [Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 The template function:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```  
  
 extracts an element, if it is possible, and stores it in `Ch`. Otherwise, it calls **is**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). In any case, it returns `Istr`.  
  
 The template function:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```  
  
 returns `Istr` >> ( `char`**\***) `str`.  
  
 The template function:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```  
  
 returns `Istr` >> ( **char&**) `Ch`.  
  
 The template function:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```  
  
 returns `Istr` >> ( **char \***) `str`.  
  
 The template function:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```  
  
 returns `Istr` >> ( **char&**) `Ch`.  
  
 The template function:  
  
```cpp  
template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
 returns `Istr` `>>` `val` (and converts an `rvalue reference` to `Istr` to an `lvalue` in the process).  
  
### <a name="example"></a>Example  
  
```cpp  
// istream_op_extract.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   ws( cin );  
   char c[10];  
  
   cin.width( 9 );  
   cin >> c;  
   cout << c << endl;  
}  
```  
  
## <a name="see-also"></a>See Also  
 [\<istream>](../standard-library/istream.md)


