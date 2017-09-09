---
title: fpos Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::fpos
- ios/std::fpos::seekpos
- ios/std::fpos::state
- ios/std::fpos::operator streamoff
dev_langs:
- C++
helpviewer_keywords:
- std::fpos [C++]
- std::fpos [C++], seekpos
- std::fpos [C++], state
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
caps.latest.revision: 20
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
ms.openlocfilehash: f26bd0d0d94f33f9e771f4c3de1547d96a773642
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="fpos-class"></a>fpos Class
The template class describes an object that can store all the information needed to restore an arbitrary file-position indicator within any stream. An object of class fpos\< **St**> effectively stores at least two member objects:  
  
-   A byte offset, of type [streamoff](../standard-library/ios-typedefs.md#streamoff).  
  
-   A conversion state, for use by an object of class basic_filebuf, of type **St**, typically `mbstate_t`.  
  
 It can also store an arbitrary file position, for use by an object of class [basic_filebuf](../standard-library/basic-filebuf-class.md), of type `fpos_t`. For an environment with limited file size, however, `streamoff` and `fpos_t` may sometimes be used interchangeably. For an environment with no streams that have a state-dependent encoding, `mbstate_t` may actually be unused. Therefore, the number of member objects stored may vary.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Statetype>  
class fpos  
```  
  
#### <a name="parameters"></a>Parameters  
 *Statetype*  
 State information.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[fpos](#fpos)|Create an object that contains information about a position (offset) in a stream.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[seekpos](#seekpos)|Used internally by the C++ Standard Library only. Do not call this method from your code.|  
|[state](#state)|Sets or returns the conversion state.|  
  
### <a name="operators"></a>Operators  
  
|||  
|-|-|  
|[operator!=](#op_neq)|Tests file-position indicators for inequality.|  
|[operator+](#op_add)|Increments a file-position indicator.|  
|[operator+=](#op_add_eq)|Increments a file-position indicator.|  
|[operator-](#operator-)|Decrements a file-position indicator.|  
|[operator-=](#operator-_eq)|Decrements a file-position indicator.|  
|[operator==](#op_eq_eq)|Tests file-position indicators for equality.|  
|[operator streamoff](#op_streamoff)|Casts object of type `fpos` to object of type `streamoff`.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<ios>  
  
 **Namespace:** std  
  
##  <a name="fpos"></a>  fpos::fpos  
 Create an object that contains information about a position (offset) in a stream.  
  
```  
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```  
  
### <a name="parameters"></a>Parameters  
 `_Off`  
 The offset into the stream.  
  
 `_State`  
 The starting state of the `fpos` object.  
  
 *_Filepos*  
 The offset into the stream.  
  
### <a name="remarks"></a>Remarks  
 The first constructor stores the offset `_Off`, relative to the beginning of file and in the initial conversion state (if that matters). If `_Off` is -1, the resulting object represents an invalid stream position.  
  
 The second constructor stores a zero offset and the object `_State`.  
  
##  <a name="op_neq"></a>  fpos::operator!=  
 Tests file-position indicators for inequality.  
  
```  
bool operator!=(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Parameters  
 `right`  
 The file-position indicator against which to compare.  
  
### <a name="return-value"></a>Return Value  
 **true** if the file-position indicators are not equal, otherwise **false**.  
  
### <a name="remarks"></a>Remarks  
 The member function returns `!(*this == right)`.  
  
### <a name="example"></a>Example  
  
```cpp  
// fpos_op_neq.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   fpos<int> pos1, pos2;  
   ifstream file;  
   char c;  
  
   // Compare two fpos object  
   if ( pos1 != pos2 )  
      cout << "File position pos1 and pos2 are not equal" << endl;  
   else  
      cout << "File position pos1 and pos2 are equal" << endl;  
  
   file.open( "fpos_op_neq.txt" );  
   file.seekg( 0 );   // Goes to a zero-based position in the file  
   pos1 = file.tellg( );  
   file.get( c);  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 += 1;  
   file.get( c );  
   cout << c << endl;  
  
   pos1 = file.tellg( ) - fpos<int>( 2);  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 = pos1 + fpos<int>( 1 );  
   file.get(c);  
   cout << c << endl;  
  
   pos1 -= fpos<int>( 2 );  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   file.close( );  
}  
```  
  
##  <a name="op_add"></a>  fpos::operator+  
 Increments a file-position indicator.  
  
```  
fpos<Statetype> operator+(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Parameters  
 `_Off`  
 The offset by which you want to increment the file-position indicator.  
  
### <a name="return-value"></a>Return Value  
 The position in the file.  
  
### <a name="remarks"></a>Remarks  
 The member function returns **fpos(\*this) +=** `_Off`.  
  
### <a name="example"></a>Example  
  See [operator!=](#op_neq) for a sample of using `operator+`.  
  
##  <a name="op_add_eq"></a>  fpos::operator+=  
 Increments a file-position indicator.  
  
```  
fpos<Statetype>& operator+=(streamoff _Off);
```  
  
### <a name="parameters"></a>Parameters  
 `_Off`  
 The offset by which you want to increment the file-position indicator.  
  
### <a name="return-value"></a>Return Value  
 The position in the file.  
  
### <a name="remarks"></a>Remarks  
 The member function adds `_Off` to the stored offset member object and then returns **\*this**. For positioning within a file, the result is generally valid only for binary streams that do not have a state-dependent encoding.  
  
### <a name="example"></a>Example  
  See [operator!=](#op_neq) for a sample of using `operator+=`.  
  
##  <a name="fpos__operator-"></a>  fpos::operator-  
 Decrements a file-position indicator.  
  
```  
streamoff operator-(const fpos<Statetype>& right) const;
 
fpos<Statetype> operator-(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Parameters  
 `right`  
 File position.  
  
 `_Off`  
 Stream offset.  
  
### <a name="return-value"></a>Return Value  
 The first member function returns `(streamoff)*this - (streamoff) right`. The second member function returns `fpos(*this) -= _Off`.  
  
### <a name="example"></a>Example  
  See [operator!=](#op_neq) for a sample of using `operator-`.  
  
##  <a name="fpos__operator-_eq"></a>  fpos::operator-=  
 Decrements a file-position indicator.  
  
```  
fpos<Statetype>& operator-=(streamoff _Off);
```  
  
### <a name="parameters"></a>Parameters  
 `_Off`  
 Stream offset.  
  
### <a name="return-value"></a>Return Value  
 The member function returns `fpos(*this) -= _Off`.  
  
### <a name="remarks"></a>Remarks  
 For positioning within a file, the result is generally valid only for binary streams that do not have a state-dependent encoding.  
  
### <a name="example"></a>Example  
  See [operator!=](#op_neq) for a sample of using `operator-=`.  
  
##  <a name="op_eq_eq"></a>  fpos::operator==  
 Tests file-position indicators for equality.  
  
```  
bool operator==(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Parameters  
 `right`  
 The file-position indicator against which to compare.  
  
### <a name="return-value"></a>Return Value  
 **true** if the file-position indicators are equal; otherwise **false**.  
  
### <a name="remarks"></a>Remarks  
 The member function returns `(streamoff)*this == (streamoff)right`.  
  
### <a name="example"></a>Example  
  See [operator!=](#op_neq) for a sample of using `operator+=`.  
  
##  <a name="op_streamoff"></a>  fpos::operator streamoff  
 Cast object of type `fpos` to object of type `streamoff`.  
  
```  
operator streamoff() const;
```  
  
### <a name="remarks"></a>Remarks  
 The member function returns the stored offset member object and any additional offset stored as part of the `fpos_t` member object.  
  
### <a name="example"></a>Example  
  
```cpp  
// fpos_op_streampos.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   streamoff s;  
   ofstream file( "rdbuf.txt");  
  
   fpos<mbstate_t> f = file.tellp( );  
   // Is equivalent to ..  
   // streampos f = file.tellp( );  
   s = f;  
   cout << s << endl;  
}  
```  
  
```Output  
0  
```  
  
##  <a name="seekpos"></a>  fpos::seekpos  
 This method is used internally by the C++ Standard Library only. Do not call this method from your code.  
  
```  
fpos_t seekpos() const;
```  
  
##  <a name="state"></a>  fpos::state  
 Sets or returns the conversion state.  
  
```  
Statetype state() const;

void state(Statetype _State);
```  
  
### <a name="parameters"></a>Parameters  
 `_State`  
 The new conversion state.  
  
### <a name="return-value"></a>Return Value  
 The conversion state.  
  
### <a name="remarks"></a>Remarks  
 The first member function returns the value stored in the **St** member object. The second member function stores `_State` in the **St** member object.  
  
### <a name="example"></a>Example  
  
```cpp  
// fpos_state.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main() {  
   using namespace std;  
   streamoff s;  
   ifstream file( "fpos_state.txt" );  
  
   fpos<mbstate_t> f = file.tellg( );  
   char ch;  
   while ( !file.eof( ) )  
      file.get( ch );  
   s = f;  
   cout << f.state( ) << endl;  
   f.state( 9 );  
   cout << f.state( ) << endl;  
}  
```  
  
## <a name="see-also"></a>See Also  
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream Programming](../standard-library/iostream-programming.md)   
 [iostreams Conventions](../standard-library/iostreams-conventions.md)


