---
title: basic_ios Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ios/std::basic_ios
- ios/std::basic_ios::char_type
- ios/std::basic_ios::int_type
- ios/std::basic_ios::off_type
- ios/std::basic_ios::pos_type
- ios/std::basic_ios::traits_type
- ios/std::basic_ios::bad
- ios/std::basic_ios::clear
- ios/std::basic_ios::copyfmt
- ios/std::basic_ios::eof
- ios/std::basic_ios::exceptions
- ios/std::basic_ios::fail
- ios/std::basic_ios::fill
- ios/std::basic_ios::good
- ios/std::basic_ios::imbue
- ios/std::basic_ios::init
- ios/std::basic_ios::move
- ios/std::basic_ios::narrow
- ios/std::basic_ios::rdbuf
- ios/std::basic_ios::rdstate
- ios/std::basic_ios::set_rdbuf
- ios/std::basic_ios::setstate
- ios/std::basic_ios::swap
- ios/std::basic_ios::tie
- ios/std::basic_ios::widen
- ios/std::basic_ios::explicit operator bool
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ios [C++]
- std::basic_ios [C++], char_type
- std::basic_ios [C++], int_type
- std::basic_ios [C++], off_type
- std::basic_ios [C++], pos_type
- std::basic_ios [C++], traits_type
- std::basic_ios [C++], bad
- std::basic_ios [C++], clear
- std::basic_ios [C++], copyfmt
- std::basic_ios [C++], eof
- std::basic_ios [C++], exceptions
- std::basic_ios [C++], fail
- std::basic_ios [C++], fill
- std::basic_ios [C++], good
- std::basic_ios [C++], imbue
- std::basic_ios [C++], init
- std::basic_ios [C++], move
- std::basic_ios [C++], narrow
- std::basic_ios [C++], rdbuf
- std::basic_ios [C++], rdstate
- std::basic_ios [C++], set_rdbuf
- std::basic_ios [C++], setstate
- std::basic_ios [C++], swap
- std::basic_ios [C++], tie
- std::basic_ios [C++], widen
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
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
ms.openlocfilehash: ea20a0c433ca12ceafc7bdcfe088d994ca65555e
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="basicios-class"></a>basic_ios Class
The template class describes the storage and member functions common to both input streams (of template class [basic_istream](../standard-library/basic-istream-class.md)) and output streams (of template class [basic_ostream](../standard-library/basic-ostream-class.md)) that depend on the template parameters. (The class [ios_base](../standard-library/ios-base-class.md) describes what is common and not dependent on template parameters.) An object of class **basic_ios\<class Elem, class Traits>** helps control a stream with elements of type **Elem**, whose character traits are determined by the class **Traits**.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
template <class Elem, class Traits>  
class basic_ios : public ios_base  
```  
  
#### <a name="parameters"></a>Parameters  
 `Elem`  
 A type.  
  
 `Traits`  
 A variable of type `char_traits`.  
  
## <a name="remarks"></a>Remarks  
 An object of class **basic_ios\<class Elem, class Traits>** stores:  
  
-   A tie pointer to an object of type [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits>**.  
  
-   A stream buffer pointer to an object of type [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits >**.  
  
- [Formatting information](../standard-library/ios-base-class.md).  
  
- [Stream state information](../standard-library/ios-base-class.md) in a base object of type [ios_base](../standard-library/ios-base-class.md).  
  
-   A fill character in an object of type `char_type`.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[basic_ios](#basic_ios)|Constructs the `basic_ios` class.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|A synonym for the template parameter `Elem`.|  
|[int_type](#int_type)|A synonym for `Traits::int_type`.|  
|[off_type](#off_type)|A synonym for `Traits::off_type`.|  
|[pos_type](#pos_type)|A synonym for `Traits::pos_type`.|  
|[traits_type](#traits_type)|A synonym for the template parameter `Traits`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[bad](#bad)|Indicates a loss of integrity of the stream buffer.|  
|[clear](#clear)|Clears all error flags.|  
|[copyfmt](#copyfmt)|Copies flags from one stream to another.|  
|[eof](#eof)|Indicates if the end of a stream has been reached.|  
|[exceptions](#exceptions)|Indicates which exceptions will be thrown by the stream.|  
|[fail](#fail)|Indicates failure to extract a valid field from a stream.|  
|[fill](#fill)|Specifies or returns the character that will be used when the text is not as wide as the stream.|  
|[good](#good)|Indicates the stream is in good condition.|  
|[imbue](#imbue)|Changes the locale.|  
|[init](#init)|Called by `basic_ios` constructors.|  
|[move](#move)|Moves all values, except the pointer to the stream buffer, from the parameter to the current object.|  
|[narrow](#narrow)|Finds the equivalent char to a given `char_type`.|  
|[rdbuf](#rdbuf)|Routes stream to specified buffer.|  
|[rdstate](#rdstate)|Reads the state of bits for flags.|  
|[set_rdbuf](#set_rdbuf)|Assigns a stream buffer to be the read buffer for this stream object.|  
|[setstate](#setstate)|Sets additional flags.|  
|[swap](#swap)|Exchanges the values in this `basic_ios` object for those of another `basic_ios` object. The pointers to the stream buffers are not swapped.|  
|[tie](#tie)|Ensures that one stream is processed before another stream.|  
|[widen](#widen)|Finds the equivalent `char_type` to a given char.|  
  
### <a name="operators"></a>Operators  
  
|||  
|-|-|  
|[explicit operator bool](#op_bool)|Allows use of a `basic_ios` object as a `bool`. Automatic type conversion is disabled to prevent common, unintended side effects.|  
|[operator void *](#op_void_star)|Indicates if the stream is still good.|  
|[operator!](#op_not)|Indicates if the stream is not bad.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<ios>  
  
 **Namespace:** std  
  
##  <a name="bad"></a>  basic_ios::bad  
 Indicates a loss of integrity of the stream buffer  
  
```  
bool bad() const;
```  
  
### <a name="return-value"></a>Return Value  
 `true` if `rdstate & badbit` is nonzero; otherwise `false`.  
  
 For more information on `badbit`, see [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_bad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.bad( );  
  cout << boolalpha;  
  cout << b << endl;  
    
  b = cout.good( );  
  cout << b << endl;  
}  
  
```  
  
##  <a name="basic_ios"></a>  basic_ios::basic_ios  
 Constructs the basic_ios class.  
  
```   
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```  
  
### <a name="parameters"></a>Parameters  
 `sb`  
 Standard buffer to store input or output elements.  
  
### <a name="remarks"></a>Remarks  
 The first constructor initializes its member objects by calling [init](#init)(_ *Sb*). The second (protected) constructor leaves its member objects uninitialized. A later call to **init** must initialize the object before it can be safely destroyed.  
  
##  <a name="char_type"></a>  basic_ios::char_type  
 A synonym for the template parameter **Elem**.  
  
```   
typedef Elem char_type;  
```  
  
##  <a name="clear"></a>  basic_ios::clear  
 Clears all error flags.  
  
```   
void clear(iostate state = goodbit, bool reraise = false); 
void clear(io_state state);
```  
  
### <a name="parameters"></a>Parameters  
 `state` (optional)  
 The flags you want to set after clearing all flags. Defaults to `goodbit`.  
  
 `reraise` (optional)  
 Specifies whether the exception should be re-raised. Defaults to `false` (will not re-raise the exception).  
  
### <a name="remarks"></a>Remarks  
 The flags are **goodbit**, **failbit**, **eofbit**, and **badbit**. Test for these flags with [good](#good), [bad](#bad), [eof](#eof), and [fail](#fail)  
  
 The member function replaces the stored stream state information with:  
  
 `state` &#124; `(`[rdbuf](#rdbuf) != 0 **goodbit** : **badbit**)  
  
 If `state`**&**[exceptions](#exceptions) is nonzero, it then throws an object of class [failure](../standard-library/ios-base-class.md#failure).  
  
### <a name="example"></a>Example  
  See [rdstate](#rdstate) and [getline](../standard-library/string-functions.md#getline) for examples using **clear**.  
  
##  <a name="copyfmt"></a>  basic_ios::copyfmt  
 Copies flags from one stream to another.  
  
```   
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```  
  
### <a name="parameters"></a>Parameters  
 `right`  
 The stream whose flags you want to copy.  
  
### <a name="return-value"></a>Return Value  
 The **this** object for the stream to which you are copying the flags.  
  
### <a name="remarks"></a>Remarks  
 The member function reports the callback event **erase\_event**. It then copies from `right` into **\*this** the fill character, the tie pointer, and the formatting information. Before altering the exception mask, it reports the callback event **copyfmt_event**. If, after the copy is complete, **state &**[exceptions](#exceptions) is nonzero, the function effectively calls [clear](#clear) with the argument [rdstate](#rdstate). It returns **\*this**.  
  
### <a name="example"></a>Example  
  
```cpp    
// basic_ios_copyfmt.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream x( "test.txt" );  
  int i = 10;  
    
  x << showpos;  
  cout << i << endl;  
  cout.copyfmt( x );  
  cout << i << endl;  
}  
  
```  
  
##  <a name="eof"></a>  basic_ios::eof  
 Indicates if the end of a stream has been reached.  
  
```  
bool eof() const;
```  
  
### <a name="return-value"></a>Return Value  
 `true` if the end of the stream has been reached, `false` otherwise.  
  
### <a name="remarks"></a>Remarks  
 The member function returns `true` if [rdstate](#rdstate) `& eofbit` is nonzero. For more information on `eofbit`, see [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Example  
  
```cpp    
// basic_ios_eof.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
int main( int argc, char* argv[] )  
{  
  fstream   fs;  
  int n = 1;  
  fs.open( "basic_ios_eof.txt" );   // an empty file  
  cout << boolalpha  
  cout << fs.eof() << endl;  
  fs >> n;   // Read the char in the file  
  cout << fs.eof() << endl;  
}  
  
```  
  
##  <a name="exceptions"></a>  basic_ios::exceptions  
 Indicates which exceptions will be thrown by the stream.  
  
```   
iostate exceptions() const; 
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```  
  
### <a name="parameters"></a>Parameters  
 *Newexcept*  
 The flags that you want to throw an exception.  
  
### <a name="return-value"></a>Return Value  
 The flags that are currently specified to thrown an exception for the stream.  
  
### <a name="remarks"></a>Remarks  
 The first member function returns the stored exception mask. The second member function stores *_Except* in the exception mask and returns its previous stored value. Note that storing a new exception mask can throw an exception just like the call [clear](#clear)( [rdstate](#rdstate) ).  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_exceptions.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
    
  cout << cout.exceptions( ) << endl;  
  cout.exceptions( ios::eofbit );  
  cout << cout.exceptions( ) << endl;  
  try  
  {  
    cout.clear( ios::eofbit );   // Force eofbit on  
  }  
  catch ( exception &e )  
  {  
    cout.clear( );  
    cout << "Caught the exception." << endl;  
    cout << "Exception class: " << typeid(e).name()  << endl;  
    cout << "Exception description: " << e.what() << endl;  
  }  
}  
  
```  
  
```Output  
  
0  
1  
Caught the exception.  
Exception class: class std::ios_base::failure  
Exception description: ios_base::eofbit set   
```  
  
##  <a name="fail"></a>  basic_ios::fail  
 Indicates failure to extract a valid field from a stream.  
  
```  
bool fail() const;
```  
  
### <a name="return-value"></a>Return Value  
 `true` if [rdstate](#rdstate) `& (badbit|failbit)` is nonzero, otherwise `false`.  
  
 For more information on `failbit`, see [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_fail.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.fail( );  
  cout << boolalpha;  
  cout << b << endl;  
}  
  
```  
  
##  <a name="fill"></a>  basic_ios::fill  
 Specifies or returns the character that will be used when the text is not as wide as the stream.  
  
```   
char_type fill() const; 
char_type fill(char_type Char);
```  
  
### <a name="parameters"></a>Parameters  
 `Char`  
 The character you want as the fill character.  
  
### <a name="return-value"></a>Return Value  
 The current fill character.  
  
### <a name="remarks"></a>Remarks  
 The first member function returns the stored fill character. The second member function stores `Char` in the fill character and returns its previous stored value.  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_fill.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iomanip>  
  
int main( )  
{  
  using namespace std;  
    
  cout << setw( 5 ) << 'a' << endl;     
  cout.fill( 'x' );  
  cout << setw( 5 ) << 'a' << endl;      
  cout << cout.fill( ) << endl;  
}  
  
```  
  
```Output  
  
a  
xxxxa  
x   
```  
  
##  <a name="good"></a>  basic_ios::good  
 Indicates the stream is in good condition.  
  
```  
bool good() const;
```  
  
### <a name="return-value"></a>Return Value  
 `true` if [rdstate](#rdstate) `== goodbit` (no state flags are set), otherwise, `false`.  
  
 For more information on `goodbit`, see [ios_base::iostate](../standard-library/ios-base-class.md#iostate).  
  
### <a name="example"></a>Example  
  See [basic_ios::bad](#bad) for an example of using `good`.  
  
##  <a name="imbue"></a>  basic_ios::imbue  
 Changes the locale.  
  
```   
locale imbue(const locale& Loc);
```  
  
### <a name="parameters"></a>Parameters  
 `Loc`  
 A locale string.  
  
### <a name="return-value"></a>Return Value  
 The previous locale.  
  
### <a name="remarks"></a>Remarks  
 If [rdbuf](#rdbuf) is not a null pointer, the member function calls  
  
 `rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *Loc*)  
  
 In any case, it returns [ios_base::imbue](../standard-library/ios-base-class.md#imbue)(_ *Loc*).  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_imbue.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <locale>  
  
int main( )  
{  
  using namespace std;  
    
  cout.imbue( locale( "french_france" ) );  
  double x = 1234567.123456;  
  cout << x << endl;  
}  
  
```  
  
##  <a name="init"></a>  basic_ios::init  
 Called by basic_ios constructors.  
  
```  
 
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```  
  
### <a name="parameters"></a>Parameters  
 `_Sb`  
 Standard buffer to store input or output elements.  
  
 `_Isstd`  
 Specifies whether this is a standard stream.  
  
### <a name="remarks"></a>Remarks  
 The member function stores values in all member objects, so that:  
  
- [rdbuf](#rdbuf) returns *_Sb.*  
  
- [tie](#tie) returns a null pointer.  
  
- [rdstate](#rdstate) returns [goodbit](../standard-library/ios-base-class.md#iostate) if `_Sb` is nonzero; otherwise, it returns [badbit](../standard-library/ios-base-class.md#iostate).  
  
- [exceptions](#exceptions) returns **goodbit**.  
  
- [flags](../standard-library/ios-base-class.md#flags) returns [skipws](../standard-library/ios-base-class.md#fmtflags) &#124; [dec](../standard-library/ios-base-class.md#fmtflags).  
  
- [width](../standard-library/ios-base-class.md#width) returns 0.  
  
- [precision](../standard-library/ios-base-class.md#precision) returns 6.  
  
- [fill](#fill) returns the space character.  
  
- [getloc](../standard-library/ios-base-class.md#getloc) returns `locale::classic`.  
  
- [iword](../standard-library/ios-base-class.md#iword) returns zero, and [pword](../standard-library/ios-base-class.md#pword) returns a null pointer for all argument values.  
  
##  <a name="int_type"></a>  basic_ios::int_type  
 A synonym for **traits_type::int_type**.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="move"></a>  basic_ios::move  
 Moves all values, except the pointer to the stream buffer, from the parameter to the current object.  
  
```   
void move(basic_ios&& right);
```  
  
### <a name="parameters"></a>Parameters  
 `right`  
 The `ios_base` object to move values from.  
  
### <a name="remarks"></a>Remarks  
 The protected member function moves all the values stored in `right` to `*this` except the stored `stream buffer pointer`, which is unchanged in `right` and set to a null pointer in `*this`. The stored `tie pointer` is set to a null pointer in `right`.  
  
##  <a name="narrow"></a>  basic_ios::narrow  
 Finds the equivalent char to a given `char_type`.  
  
```  
char narrow(char_type Char, char Default = '\0') const;
```  
  
### <a name="parameters"></a>Parameters  
 `Char`  
 The `char` to convert.  
  
 `Default`  
 The `char` that you want returned if no equivalent is found.  
  
### <a name="return-value"></a>Return Value  
 The equivalent `char` to a given `char_type`.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [use_facet](../standard-library/basic-filebuf-class.md#open)\<ctype\<E> >( [getloc](../standard-library/ios-base-class.md#getloc)( ) ).`narrow`( `Char`, `Default`).  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_narrow.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  wchar_t *x = L"test";  
  char y[10];  
  cout << x[0] << endl;  
  wcout << x << endl;  
  y[0] = wcout.narrow( x[0] );  
  cout << y[0] << endl;  
}  
```  
  
##  <a name="off_type"></a>  basic_ios::off_type  
 A synonym for **traits_type::off_type**.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="op_void_star"></a>  basic_ios::operator void *  
 Indicates if the stream is still good.  
  
```  
 operator void *() const;
```  
  
### <a name="return-value"></a>Return Value  
 The operator returns a null pointer only if [fail](#fail).  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_opgood.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << (bool)(&cout != 0) << endl;   // Stream is still good  
}  
  
```  
  
```Output  
1  
```  
  
##  <a name="op_not"></a>  basic_ios::operator!  
 Indicates if the stream is not bad.  
  
```   
bool operator!() const;
```  
  
### <a name="return-value"></a>Return Value  
 Returns [fail](#fail).  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_opbad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << !cout << endl;   // Stream is not bad  
}  
  
```  
  
```Output  
0  
```  
  
##  <a name="op_bool"></a>  basic_ios::operator bool  
 Allows use of a `basic_ios` object as a `bool`. Automatic type conversion is disabled to prevent common, unintended side effects.  
  
```  
explicit operator bool() const;
```  
  
### <a name="remarks"></a>Remarks  
 The operator returns a value convertible to `false` only if `fail()`. The return type is convertible only to `bool`, not to `void *` or other known scalar type.  
  
##  <a name="pos_type"></a>  basic_ios::pos_type  
 A synonym for **traits_type::pos_type**.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="rdbuf"></a>  basic_ios::rdbuf  
 Routes stream to specified buffer.  
  
```   
basic_streambuf<Elem, Traits> *rdbuf() const; 
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```  
  
### <a name="parameters"></a>Parameters  
 `_Sb`  
 A stream.  
  
### <a name="remarks"></a>Remarks  
 The first member function returns the stored stream buffer pointer.  
  
 The second member function stores `_Sb` in the stored stream buffer pointer and returns the previously stored value.  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_rdbuf.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream file( "rdbuf.txt" );  
  streambuf *x = cout.rdbuf( file.rdbuf( ) );  
  cout << "test" << endl;   // Goes to file  
  cout.rdbuf(x);  
  cout << "test2" << endl;  
}  
  
```  
  
```Output  
test2  
```  
  
##  <a name="rdstate"></a>  basic_ios::rdstate  
 Reads the state of bits for flags.  
  
```  
 
iostate rdstate() const;
```  
  
### <a name="return-value"></a>Return Value  
 The stored stream state information.  
  
### <a name="example"></a>Example  
  
```cpp  
// basic_ios_rdstate.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
void TestFlags( ios& x )  
{  
  cout << ( x.rdstate( ) & ios::badbit ) << endl;  
  cout << ( x.rdstate( ) & ios::failbit ) << endl;  
  cout << ( x.rdstate( ) & ios::eofbit ) << endl;  
  cout << endl;  
}  
  
int main( )  
{  
  fstream x( "c:\test.txt", ios::out );  
  x.clear( );  
  TestFlags( x );  
  x.clear( ios::badbit | ios::failbit | ios::eofbit );  
  TestFlags( x );  
}  
  
```  
  
```Output  
  
0  
0  
0  
  
4  
2  
1   
```  
  
##  <a name="setstate"></a>  basic_ios::setstate  
 Sets additional flags.  
  
```   
void setstate(iostate _State);
```  
  
### <a name="parameters"></a>Parameters  
 `_State`  
 Additional flags to set.  
  
### <a name="remarks"></a>Remarks  
 The member function effectively calls [clear](#clear)(_ *State* &#124; [rdstate](#rdstate)).  
  
### <a name="example"></a>Example  
  
```cpp    
// basic_ios_setstate.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
  bool b = cout.bad( );  
  cout << b << endl;   // Good  
  cout.clear( ios::badbit );  
  b = cout.bad( );  
  // cout.clear( );  
  cout << b << endl;   // Is bad, good  
  b = cout.fail( );  
  cout << b << endl;   // Not failed  
  cout.setstate( ios::failbit );  
  b = cout.fail( );  
  cout.clear( );  
  cout << b << endl;   // Is failed, good  
  return 0;  
}  
  
```  
  
```Output  
  
0  
1   
```  
  
##  <a name="set_rdbuf"></a>  basic_ios::set_rdbuf  
 Assigns a stream buffer to be the read buffer for this stream object.  
  
```   
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)  
```  
  
### <a name="parameters"></a>Parameters  
 `strbuf`  
 The stream buffer to become the read buffer.  
  
### <a name="remarks"></a>Remarks  
 The protected member function stores `strbuf` in the `stream buffer pointer`.It does not call `clear`.  
  
##  <a name="tie"></a>  basic_ios::tie  
 Ensures that one stream is processed before another stream.  
  
```  
 
basic_ostream<Elem, Traits> *tie() const; 
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```  
  
### <a name="parameters"></a>Parameters  
 `str`  
 A stream.  
  
### <a name="return-value"></a>Return Value  
 The first member function returns the stored tie pointer. The second member function stores `str` in the tie pointer and returns its previous stored value.  
  
### <a name="remarks"></a>Remarks  
 `tie` causes two streams to be synchronized, such that, operations on one stream occur after operations on the other stream are complete.  
  
### <a name="example"></a>Example  
  In this example, by tying cin to cout, it is guaranteed that the "Enter a number:" string will go to the console before the number itself is extracted from cin. This eliminates the possibility that the "Enter a number:" string is still sitting in the buffer when the number is read, so that we are certain that the user actually has some prompt to respond to. By default, cin and cout are tied.  
  
```  
  
#include <ios>  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  int i;  
  cin.tie( &cout );  
  cout << "Enter a number:";  
  cin >> i;  
}  
  
```  
  
##  <a name="traits_type"></a>  basic_ios::traits_type  
 A synonym for the template parameter **Traits**.  
  
```   
typedef Traits traits_type;  
```  
  
##  <a name="widen"></a>  basic_ios::widen  
 Finds the equivalent `char_type` to a given `char`.  
  
```   
char_type widen(char Char) const;
```  
  
### <a name="parameters"></a>Parameters  
 `Char`  
 The character to convert.  
  
### <a name="return-value"></a>Return Value  
 Finds the equivalent `char_type` to a given `char`.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#getloc)). `widen`( `Char`).  
  
### <a name="example"></a>Example  
  
```cpp    
// basic_ios_widen.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  char *z = "Hello";  
  wchar_t y[2] = {0,0};  
  cout << z[0] << endl;  
  y[0] = wcout.widen( z[0] );  
  wcout << &y[0] << endl;  
}  
  
```  
  
##  <a name="swap"></a>  basic_ios::swap  
 Exchanges the values in this `basic_ios` object for those of another `basic_ios` object. However, the pointers to the stream buffers are not swapped.  
  
```   
void swap(basic_ios&& right);
```  
  
### <a name="parameters"></a>Parameters  
 `right`  
 The `basic_ios` object that is used to exchange values.  
  
### <a name="remarks"></a>Remarks  
 The protected member function exchanges all the values stored in `right` with `*this` except the stored `stream buffer pointer`.  
  
## <a name="see-also"></a>See Also  
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream Programming](../standard-library/iostream-programming.md)   
 [iostreams Conventions](../standard-library/iostreams-conventions.md)


