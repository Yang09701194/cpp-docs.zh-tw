---
title: istrstream Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs:
- C++
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 20
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
ms.openlocfilehash: 79a3e8b3d0aca0f711d1d49e8c73da8a11592b69
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="istrstream-class"></a>istrstream Class
Describes an object that controls extraction of elements and encoded objects from a stream buffer of class [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```
class istrstream : public istream
```  
  
## <a name="remarks"></a>Remarks  
 The object stores an object of class `strstreambuf`.  
  
> [!NOTE]
>  This class is deprecated. Consider using [istringstream](../standard-library/sstream-typedefs.md#istringstream) or [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) instead.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[istrstream](#istrstream)|Constructs an object of type `istrstream`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Returns a pointer to the stream's associated `strstreambuf` object.|  
|[str](#str)|Calls [freeze](../standard-library/strstreambuf-class.md#freeze), and then returns a pointer to the beginning of the controlled sequence.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<strstream>  
  
 **Namespace:** std  
  
##  <a name="istrstream"></a>  istrstream::istrstream  
 Constructs an object of type `istrstream`.  
  
```
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```  
  
### <a name="parameters"></a>Parameters  
 `count`  
 The length of the buffer ( `ptr`).  
  
 `ptr`  
 The contents with which the buffer is initialized.  
  
### <a name="remarks"></a>Remarks  
 All the constructors initialize the base class by calling [istream](../standard-library/istream-typedefs.md#istream)( **sb**), where **sb** is the stored object of class [strstreambuf](../standard-library/strstreambuf-class.md). The first two constructors also initialize **sb** by calling `strstreambuf`( ( **const**`char` \*) `ptr`, 0 ). The remaining two constructors instead call `strstreambuf`( ( **const**`char` *) `ptr`, `count` ).  
  
##  <a name="rdbuf"></a>  istrstream::rdbuf  
 Returns a pointer to the stream's associated strstreambuf object.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to the stream's associated strstreambuf object.  
  
### <a name="remarks"></a>Remarks  
 The member function returns the address of the stored stream buffer, of type pointer to [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Example  
  See [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) for a sample that uses `rdbuf`.  
  
##  <a name="str"></a>  istrstream::str  
 Calls [freeze](../standard-library/strstreambuf-class.md#freeze), and then returns a pointer to the beginning of the controlled sequence.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Return Value  
 A pointer to the beginning of the controlled sequence.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).  
  
### <a name="example"></a>Example  
  See [strstream::str](../standard-library/strstreambuf-class.md#str) for a sample that uses **str**.  
  
## <a name="see-also"></a>See Also  
 [istream](../standard-library/istream-typedefs.md#istream)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream Programming](../standard-library/iostream-programming.md)   
 [iostreams Conventions](../standard-library/iostreams-conventions.md)




