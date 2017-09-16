---
title: basic_stringstream Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
caps.latest.revision: 19
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
ms.openlocfilehash: 60b73189130f32c8d892b51469a7427805065b8a
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="basicstringstream-class"></a>basic_stringstream Class
Describes an object that controls insertion and extraction of elements and encoded objects using a stream buffer of class [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_stringstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parameters  
 `Alloc`  
 The allocator class.  
  
 `Elem`  
 The type of the basic element of the string.  
  
 *Tr*  
 The character traits specialized on the basic element of the string.  
  
## <a name="remarks"></a>Remarks  
 The template class describes an object that controls insertion and extraction of elements and encoded objects using a stream buffer of class [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, with elements of type **Elem**, whose character traits are determined by the class **Tr**, and whose elements are allocated by an allocator of class `Alloc`. The object stores an object of class basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[basic_stringstream](#basic_stringstream)|Constructs an object of type `basic_stringstream`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|The type is a synonym for the template parameter `Alloc`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Returns the address of the stored stream buffer of type `pointer` to [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|  
|[str](#str)|Sets or gets the text in a string buffer without changing the write position.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<sstream>  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>  basic_stringstream::allocator_type  
 The type is a synonym for the template parameter `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_stringstream"></a>  basic_stringstream::basic_stringstream  
 Constructs an object of type `basic_stringstream`.  
  
```  
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parameters  
 `_Mode`  
 One of the enumerations in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 An object of type `basic_string`.  
  
### <a name="remarks"></a>Remarks  
 The first constructor initializes the base class by calling [basic_iostream](../standard-library/basic-iostream-class.md)( **sb**), where **sb** is the stored object of class [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>. It also initializes **sb** by calling basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode`).  
  
 The second constructor initializes the base class by calling basic_iostream( **sb**). It also initializes **sb** by calling basic_stringbuf< **Elem**, **Tr**, `Alloc`>(_ *Str*, `_Mode`).  
  
##  <a name="rdbuf"></a>  basic_stringstream::rdbuf  
 Returns the address of the stored stream buffer of type **pointer** to [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Return Value  
 The address of the stored stream buffer of type **pointer** to basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="example"></a>Example  
  See [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) for an example that uses `rdbuf`.  
  
##  <a name="str"></a>  basic_stringstream::str  
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
 Returns an object of class [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, whose controlled sequence is a copy of the sequence controlled by **\*this**.  
  
### <a name="remarks"></a>Remarks  
 The first member function returns [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). The second member function calls `rdbuf` -> **str**( `_Newstr`).  
  
### <a name="example"></a>Example  
  See [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) for an example that uses **str**.  
  
## <a name="see-also"></a>See Also  
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream Programming](../standard-library/iostream-programming.md)   
 [iostreams Conventions](../standard-library/iostreams-conventions.md)


