---
title: ostreambuf_iterator Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
dev_langs:
- C++
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 16
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
ms.openlocfilehash: 089009873b69087b1125ef3e1dc7b1c907dce956
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="ostreambufiterator-class"></a>ostreambuf_iterator Class
The template class ostreambuf_iterator describes an output iterator object that writes successive character elements onto the output stream with the extraction **operator>>**. The `ostreambuf_iterator`s differ from those of the [ostream_iterator Class](../standard-library/ostream-iterator-class.md) in having characters instead of a generic type at the type of object being inserted into the output stream.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType = char class Traits = char_traits <CharType>>
```  
  
#### <a name="parameters"></a>Parameters  
 `CharType`  
 The type that represents the character type for the ostreambuf_iterator. This argument is optional and the default value is `char`.  
  
 `Traits`  
 The type that represents the character type for the ostreambuf_iterator. This argument is optional and the default value is `char_traits`\< *CharType>.*  
  
## <a name="remarks"></a>Remarks  
 The ostreambuf_iterator class must satisfy the requirements for an output iterator. Algorithms can be written directly to output streams using an `ostreambuf_iterator`. The class provides a low-level stream iterator that allows access to the raw (unformatted) I/O stream in the form of characters and the ability to bypass the buffering and character translations associated with the high-level stream iterators.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Constructs an `ostreambuf_iterator` that is initialized to write characters to the output stream.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|A type that provides for the character type of the `ostreambuf_iterator`.|  
|[ostream_type](#ostreambuf_iterator_ostream_type)|A type that provides for the stream type of the `ostream_iterator`.|  
|[streambuf_type](#streambuf_type)|A type that provides for the stream type of the `ostreambuf_iterator`.|  
|[traits_type](#traits_type)|A type that provides for the character traits type of the `ostream_iterator`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[failed](#failed)|Tests for failure of an insertion into the output stream buffer.|  
  
### <a name="operators"></a>Operators  
  
|||  
|-|-|  
|[operator*](#op_star)|Dereferencing operator used to implement the output iterator expression * `i` = `x`.|  
|[operator++](#op_add_add)|A nonfunctional increment operator that returns an `ostreambuf_iterator` to the same object it addressed before the operation was called.|  
|[operator=](#op_eq)|The operator inserts a character into the associated stream buffer.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  ostreambuf_iterator::char_type  
 A type that provides for the character type of the `ostreambuf_iterator`.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **CharType**.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostreambuf_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
##  <a name="failed"></a>  ostreambuf_iterator::failed  
 Tests for failure of an insertion into the output stream buffer.  
  
```
bool failed() const throw();
```  
  
### <a name="return-value"></a>Return Value  
 **true** if no insertion into the output stream buffer has failed earlier; otherwise **false**.  
  
### <a name="remarks"></a>Remarks  
 The member function returns **true** if, in any prior use of member `operator=`, the call to **subf**_-> `sputc` returned **eof**.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostreambuf_iterator_failed.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'a';  
   charOut ++;  
 *charOut  = 'b';  
   charOut ++;     
 *charOut = 'c';  
   cout << " are characters output individually." << endl;  
  
   bool b1 = charOut.failed ( );  
   if (b1)   
       cout << "At least one insertion failed." << endl;  
   else  
       cout << "No insertions failed." << endl;  
}  
\* Output:   
abc are characters output individually.  
No insertions failed.  
*\  
```  
  
##  <a name="op_star"></a>  ostreambuf_iterator::operator*  
 A nonfunctional dereferencing operator used to implement the output iterator expression \* *i* = *x*.  
  
```
ostreambuf_iterator<CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>Return Value  
 The ostreambuf iterator object.  
  
### <a name="remarks"></a>Remarks  
 This operator functions only in the output iterator expression \* *i* = *x* to output characters to stream buffer. Applied to an ostreambuf iterator, it returns the iterator; **\*iter** returns **iter**,  
  
### <a name="example"></a>Example  
  
```cpp  
// ostreambuf_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;   // no effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';  
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_add_add"></a>  ostreambuf_iterator::operator++  
 A nonfunctional increment operator that returns an ostream iterator to the same character it addressed before the operation was called.  
  
```
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```  
  
### <a name="return-value"></a>Return Value  
 A reference to the character originally addressed or to an implementation-defined object that is convertible to `ostreambuf_iterator`\< **CharType**, **Traits**>.  
  
### <a name="remarks"></a>Remarks  
 The operator is used to implement the output iterator expression \* *i* = *x*.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostreambuf_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_eq"></a>  ostreambuf_iterator::operator=  
 The operator inserts a character into the associated stream buffer.  
  
```
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```  
  
### <a name="parameters"></a>Parameters  
 `_Char`  
 The character to be inserted into the stream buffer.  
  
### <a name="return-value"></a>Return Value  
 A reference to the character inserted into the stream buffer.  
  
### <a name="remarks"></a>Remarks  
 Assignment operator used to implement the output iterator expression \* *i* = *x* for writing to an output stream.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostreambuf_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostreambuf_iterator"></a>  ostreambuf_iterator::ostreambuf_iterator  
 Constructs an `ostreambuf_iterator` that is initialized to write characters to the output stream.  
  
```
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```  
  
### <a name="parameters"></a>Parameters  
 `strbuf`  
 The output streambuf object used to initialize the output stream-buffer pointer.  
  
 `Ostr`  
 The output stream object used to initialize the output stream-buffer pointer.  
  
### <a name="remarks"></a>Remarks  
 The first constructor initializes the output stream-buffer pointer with `strbuf`.  
  
 The second constructor initializes the output stream-buffer pointer with `Ostr`. `rdbuf`. The stored pointer must not be a null pointer.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostreambuf_iteratorOstreambuf_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'O';  
   charOut ++;  
 *charOut  = 'U';  
   charOut ++;     
 *charOut = 'T';  
   cout << " are characters output individually." << endl;  
  
   ostreambuf_iterator<char> strOut ( cout );  
   string str = "These characters are being written to the output stream.\n ";  
   copy ( str.begin ( ), str. end ( ), strOut );  
}  
\* Output:   
OUT are characters output individually.  
These characters are being written to the output stream.  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostream_type"></a>  ostreambuf_iterator::ostream_type  
 A type that provides for the stream type of the `ostream_iterator`.  
  
```
typedef basicOstream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for `basicOstream`\< **CharType**, **Traits**>  
  
### <a name="example"></a>Example  
  See [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) for an example of how to declare and use `ostream_type`.  
  
##  <a name="streambuf_type"></a>  ostreambuf_iterator::streambuf_type  
 A type that provides for the stream type of the `ostreambuf_iterator`.  
  
```
typedef basic_streambuf<CharType, Traits> streambuf_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for `basic_streambuf`\< **CharType**, **Traits**>, a stream class for I/O buffers that becomes `streambuf` when specialized to character type `char`.  
  
### <a name="example"></a>Example  
  See [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) for an example of how to declare and use `streambuf_type`.  
  
##  <a name="traits_type"></a>  ostreambuf_iterator::traits_type  
 A type that provides for the character traits type of the `ostream_iterator`.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **Traits**.  
  
### <a name="example"></a>Example  
  
```cpp  
// ostreambuf_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
## <a name="see-also"></a>See Also  
 [\<iterator>](../standard-library/iterator.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standard Library Reference](../standard-library/cpp-standard-library-reference.md)




