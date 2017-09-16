---
title: basic_stringbuf Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
dev_langs:
- C++
helpviewer_keywords:
- std::basic_stringbuf [C++]
- std::basic_stringbuf [C++], allocator_type
- std::basic_stringbuf [C++], char_type
- std::basic_stringbuf [C++], int_type
- std::basic_stringbuf [C++], off_type
- std::basic_stringbuf [C++], pos_type
- std::basic_stringbuf [C++], traits_type
- std::basic_stringbuf [C++], overflow
- std::basic_stringbuf [C++], pbackfail
- std::basic_stringbuf [C++], seekoff
- std::basic_stringbuf [C++], seekpos
- std::basic_stringbuf [C++], str
- std::basic_stringbuf [C++], underflow
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
caps.latest.revision: 28
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
ms.openlocfilehash: fd162dff71b079a10d1e1bcfdd2384ca53559724
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="basicstringbuf-class"></a>basic_stringbuf Class
Describes a stream buffer that controls the transmission of elements of type `Elem`, whose character traits are determined by the class `Tr`, to and from a sequence of elements stored in an array object.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem>,   
    class Alloc = allocator<Elem>>  
class basic_stringbuf : public basic_streambuf<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parameters  
 `Alloc`  
 The allocator class.  
  
 `Elem`  
 The type of the basic element of the string.  
  
 `Tr`  
 The character traits specialized on the basic element of the string.  
  
## <a name="remarks"></a>Remarks  
 The object is allocated, extended, and freed as necessary to accommodate changes in the sequence.  
  
 An object of class basic_stringbuf< `Elem`, `Tr`, `Alloc`> stores a copy of the `ios_base::`[openmode](../standard-library/ios-base-class.md#openmode) argument from its constructor as its `stringbuf` mode **mode**:  
  
-   If `mode & ios_base::in` is nonzero, the input buffer is accessible. For more information, see [basic_streambuf Class](../standard-library/basic-streambuf-class.md).  
  
-   If `mode & ios_base::out` is nonzero, the output buffer is accessible.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[basic_stringbuf](#basic_stringbuf)|Constructs an object of type `basic_stringbuf`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|The type is a synonym for the template parameter `Alloc`.|  
|[char_type](#char_type)|Associates a type name with the `Elem` template parameter.|  
|[int_type](#int_type)|Makes this type within `basic_filebuf`'s scope equivalent to the type of the same name in the `Tr` scope.|  
|[off_type](#off_type)|Makes this type within `basic_filebuf`'s scope equivalent to the type of the same name in the `Tr` scope.|  
|[pos_type](#pos_type)|Makes this type within `basic_filebuf`'s scope equivalent to the type of the same name in the `Tr` scope.|  
|[traits_type](#traits_type)|Associates a type name with the `Tr` template parameter.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[overflow](#overflow)|A protected, virtual function that can be called when a new character is inserted into a full buffer.|  
|[pbackfail](#pbackfail)|The protected virtual member function tries to put back an element into the input buffer, then makes it the current element (pointed to by the next pointer).|  
|[seekoff](#seekoff)|The protected virtual member function tries to alter the current positions for the controlled streams.|  
|[seekpos](#seekpos)|The protected virtual member function tries to alter the current positions for the controlled streams.|  
|[str](#str)|Sets or gets the text in a string buffer without changing the write position.|  
|swap||  
|[underflow](#underflow)|The protected virtual member function to extract the current element from the input stream.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<sstream>  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>  basic_stringbuf::allocator_type  
 The type is a synonym for the template parameter `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_stringbuf"></a>  basic_stringbuf::basic_stringbuf  
 Constructs an object of type `basic_stringbuf`.  
  
```  
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parameters  
 `_Mode`  
 One of the enumerations in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 An object of type [basic_string](../standard-library/basic-string-class.md).  
  
### <a name="remarks"></a>Remarks  
 The first constructor stores a null pointer in all the pointers controlling the input buffer and the output buffer. For more information, see the Remarks section of the [basic_streambuf Class](../standard-library/basic-streambuf-class.md). It also stores `_Mode` as the stringbuf mode. For more information, see the Remarks section of the [basic_stringbuf Class](../standard-library/basic-stringbuf-class.md).  
  
 The second constructor allocates a copy of the sequence controlled by the string object `str`. If `_Mode & ios_base::in` is nonzero, it sets the input buffer to start reading at the start of the sequence. If `_Mode & ios_base::out` is nonzero, it sets the output buffer to begin writing at the start of the sequence. It also stores `_Mode` as the stringbuf mode. For more information, see the Remarks section of the [basic_stringbuf Class](../standard-library/basic-stringbuf-class.md).  
  
##  <a name="char_type"></a>  basic_stringbuf::char_type  
 Associates a type name with the **Elem** template parameter.  
  
```  
typedef Elem char_type;  
```  
  
##  <a name="int_type"></a>  basic_stringbuf::int_type  
 Makes this type within basic_filebuf's scope equivalent to the type of the same name in the **Tr** scope.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="off_type"></a>  basic_stringbuf::off_type  
 Makes this type within basic_filebuf's scope equivalent to the type of the same name in the **Tr** scope.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="overflow"></a>  basic_stringbuf::overflow  
 A protected virtual function that can be called when a new character is inserted into a full buffer.  
  
```  
virtual int_type overflow(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>Parameters  
 `_Meta`  
 The character to insert into the buffer, or **traits_type::eof**.  
  
### <a name="return-value"></a>Return Value  
 If the function cannot succeed, it returns **traits_type::eof**. Otherwise, it returns **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).  
  
### <a name="remarks"></a>Remarks  
 If _ *Meta* does not compare equal to **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), the protected virtual member function tries to insert the element **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) into the output buffer. It can do so in various ways:  
  
-   If a write position is available, it can store the element into the write position and increment the next pointer for the output buffer.  
  
-   It can make a write position available by allocating new or additional storage for the output buffer. Extending the output buffer this way also extends any associated input buffer.  
  
##  <a name="pbackfail"></a>  basic_stringbuf::pbackfail  
 The protected virtual member function tries to put back an element into the input buffer, and then make it the current element (pointed to by the next pointer).  
  
```  
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>Parameters  
 `_Meta`  
 The character to insert into the buffer, or **traits_type::eof**.  
  
### <a name="return-value"></a>Return Value  
 If the function cannot succeed, it returns **traits_type::eof**. Otherwise, it returns **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).  
  
### <a name="remarks"></a>Remarks  
 If `_Meta` compares equal to **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), the element to push back is effectively the one already in the stream before the current element. Otherwise, that element is replaced by **byte** = **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta*). The function can put back an element in various ways:  
  
-   If a putback position is available, and the element stored there compares equal to byte, it can decrement the next pointer for the input buffer.  
  
-   If a putback position is available, and if the stringbuf mode permits the sequence to be altered ( **mode & ios_base::out** is nonzero), it can store byte into the putback position and decrement the next pointer for the input buffer.  
  
##  <a name="pos_type"></a>  basic_stringbuf::pos_type  
 Makes this type within basic_filebuf's scope equivalent to the type of the same name in the **Tr** scope.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="seekoff"></a>  basic_stringbuf::seekoff  
 The protected virtual member function tries to alter the current positions for the controlled streams.  
  
```  
virtual pos_type seekoff(
    off_type _Off,  
    ios_base::seekdir _Way,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parameters  
 `_Off`  
 The position to seek for relative to `_Way`. For more information, see [basic_stringbuf::off_type](#off_type).  
  
 `_Way`  
 The starting point for offset operations. See [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) for possible values.  
  
 `_Mode`  
 Specifies the mode for the pointer position. The default is to allow you to modify the read and write positions. For more information, see [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
### <a name="return-value"></a>Return Value  
 Returns the new position or an invalid stream position.  
  
### <a name="remarks"></a>Remarks  
 For an object of class `basic_stringbuf<Elem, Tr, Alloc>`, a stream position consists purely of a stream offset. Offset zero designates the first element of the controlled sequence.  
  
 The new position is determined as follows:  
  
-   If `_Way` == `ios_base::beg`, the new position is the beginning of the stream plus `_Off`.  
  
-   If `_Way` == `ios_base::cur`, the new position is the current stream position plus `_Off`.  
  
-   If `_Way` == `ios_base::end`, the new position is the end of the stream plus `_Off`.  
  
 If `_Mode & ios_base::in` is nonzero, the function alters the next position to read in the input buffer. If `_Mode & ios_base::out` is nonzero, the function alters the next position to write in the output buffer. For a stream to be affected, its buffer must exist. For a positioning operation to succeed, the resulting stream position must lie within the controlled sequence. If the function affects both stream positions, `_Way` must be `ios_base::beg` or `ios_base::end` and both streams are positioned at the same element. Otherwise (or if neither position is affected), the positioning operation fails.  
  
 If the function succeeds in altering either or both of the stream positions, it returns the resultant stream position. Otherwise, it fails and returns an invalid stream position.  
  
##  <a name="seekpos"></a>  basic_stringbuf::seekpos  
 The protected virtual member function tries to alter the current positions for the controlled streams.  
  
```  
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parameters  
 `_Sp`  
 The position to seek for.  
  
 `_Mode`  
 Specifies the mode for the pointer position. The default is to allow you to modify the read and write positions.  
  
### <a name="return-value"></a>Return Value  
 If the function succeeds in altering either or both of the stream positions, it returns the resultant stream position. Otherwise, it fails and returns an invalid stream position. To determine if the stream position is invalid, compare the return value with `pos_type(off_type(-1))`.  
  
### <a name="remarks"></a>Remarks  
 For an object of class basic_stringbuf< **Elem**, **Tr**, `Alloc`>, a stream position consists purely of a stream offset. Offset zero designates the first element of the controlled sequence. The new position is determined by _ *Sp*.  
  
 If **mode & ios_base::in** is nonzero, the function alters the next position to read in the input buffer. If **mode & ios_base::out** is nonzero, the function alters the next position to write in the output buffer. For a stream to be affected, its buffer must exist. For a positioning operation to succeed, the resulting stream position must lie within the controlled sequence. Otherwise (or if neither position is affected), the positioning operation fails.  
  
##  <a name="str"></a>  basic_stringbuf::str  
 Sets or gets the text in a string buffer without changing the write position.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>Parameters  
 `_Newstr`  
 The new string.  
  
### <a name="return-value"></a>Return Value  
 Returns an object of class [basic_string](../standard-library/basic-string-class.md)\< **Elem**, **Tr**, Alloc **>,** whose controlled sequence is a copy of the sequence controlled by **\*this**.  
  
### <a name="remarks"></a>Remarks  
 The first member function returns an object of class basic_string< **Elem**, **Tr**, `Alloc`>, whose controlled sequence is a copy of the sequence controlled by **\*this**. The sequence copied depends on the stored stringbuf mode:  
  
-   If **mode & ios_base::out** is nonzero and an output buffer exists, the sequence is the entire output buffer ( [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) elements beginning with `pbase`).  
  
-   If **mode & ios_base::in** is nonzero and an input buffer exists, the sequence is the entire input buffer ( [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) elements beginning with `eback`).  
  
-   Otherwise, the copied sequence is empty.  
  
 The second member function deallocates any sequence currently controlled by **\*this**. It then allocates a copy of the sequence controlled by `_Newstr`. If **mode & ios_base::in** is nonzero, it sets the input buffer to start reading at the beginning of the sequence. If **mode & ios_base::out** is nonzero, it sets the output buffer to start writing at the beginning of the sequence.  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_stringbuf_str.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )   
{  
   basic_string<char> i( "test" );  
   stringstream ss;  
  
   ss.rdbuf( )->str( i );  
   cout << ss.str( ) << endl;  
  
   ss << "z";  
   cout << ss.str( ) << endl;  
  
   ss.rdbuf( )->str( "be" );  
   cout << ss.str( ) << endl;  
}  
```  
  
```Output  
test  
zest  
be  
```  
  
##  <a name="traits_type"></a>  basic_stringbuf::traits_type  
 Associates a type name with the **Tr** template parameter.  
  
```  
typedef Tr traits_type;  
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **Tr**.  
  
##  <a name="underflow"></a>  basic_stringbuf::underflow  
 Protected, virtual function to extract the current element from the input stream.  
  
```  
virtual int_type underflow();
```  
  
### <a name="return-value"></a>Return Value  
 If the function cannot succeed, it returns **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). Otherwise, it returns the current element in the input stream, which are converted.  
  
### <a name="remarks"></a>Remarks  
 The protected virtual member function tries to extract the current element **byte** from the input buffer, advance the current stream position, and return the element as **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **byte**). It can do so in one way: If a read position is available, it takes **byte** as the element stored in the read position and advances the next pointer for the input buffer.  
  
##  <a name="swap"></a>  basic_streambuf::swap  
 Swaps the contents of this string buffer with another string buffer.  
  
```  
void basic_stringbuf<T>::swap(basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>Parameters  
 `other`  
 The basic_stringbuf whose contents will be swapped with this basic_stringbuf.  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="op_eq"></a>  basic_stringbuf::operator=  
 Assigns the contents of the basic_stringbuf on the right side of the operator to the basic_stringbuf on the left side.  
  
```  
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>Parameters  
 `other`  
 A basic_stringbuf whose contents, including locale traits, will be assigned to the stringbuf on the left side of the operator.  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>See Also  
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream Programming](../standard-library/iostream-programming.md)   
 [iostreams Conventions](../standard-library/iostreams-conventions.md)


