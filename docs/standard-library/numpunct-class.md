---
title: numpunct Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocnum/std::numpunct
- locale/std::numpunct::char_type
- locale/std::numpunct::string_type
- locale/std::numpunct::decimal_point
- locale/std::numpunct::do_decimal_point
- locale/std::numpunct::do_falsename
- locale/std::numpunct::do_grouping
- locale/std::numpunct::do_thousands_sep
- locale/std::numpunct::do_truename
- locale/std::numpunct::falsename
- locale/std::numpunct::grouping
- locale/std::numpunct::thousands_sep
- locale/std::numpunct::truename
dev_langs:
- C++
helpviewer_keywords:
- std::numpunct [C++]
- std::numpunct [C++], char_type
- std::numpunct [C++], string_type
- std::numpunct [C++], decimal_point
- std::numpunct [C++], do_decimal_point
- std::numpunct [C++], do_falsename
- std::numpunct [C++], do_grouping
- std::numpunct [C++], do_thousands_sep
- std::numpunct [C++], do_truename
- std::numpunct [C++], falsename
- std::numpunct [C++], grouping
- std::numpunct [C++], thousands_sep
- std::numpunct [C++], truename
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 22
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
ms.openlocfilehash: aaaeb63198a6ff5191f5bb758c90c0d41d3dc4c4
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="numpunct-class"></a>numpunct Class
A template class that describes an object that can serve as a local facet to describe the sequences of type `CharType` used to represent information about the formatting and punctuation of numeric and Boolean expressions.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>Parameters  
 `CharType`  
 The type used within a program to encode characters in a locale.  
  
## <a name="remarks"></a>Remarks  
 As with any locale facet, the static object ID has an initial stored value of zero. The first attempt to access its stored value stores a unique positive value in **id.**  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[numpunct](#numpunct)|The constructor for objects of type `numpunct`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|A type that is used to describe a character used by a locale.|  
|[string_type](#string_type)|A type that describes a string containing characters of type `CharType`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[decimal_point](#decimal_point)|Returns a locale-specific element to use as a decimal point.|  
|[do_decimal_point](#do_decimal_point)|A protected virtual member function that is called to return a locale-specific element to use as a decimal point.|  
|[do_falsename](#do_falsename)|A protected virtual member function that is called to return a string to use as a text representation of the value `false`.|  
|[do_grouping](#do_grouping)|A protected virtual member function that is called to return a locale-specific rule for determining how digits are grouped to the left of any decimal point.|  
|[do_thousands_sep](#do_thousands_sep)|A protected virtual member function that is called to return a locale-specific element to use as a thousands separator.|  
|[do_truename](#do_truename)|A protected virtual member function that is called to return a string to use as a text representation of the value `true`.|  
|[falsename](#falsename)|Returns a string to use as a text representation of the value `false`.|  
|[grouping](#grouping)|Returns a locale-specific rule for determining how digits are grouped to the left of any decimal point.|  
|[thousands_sep](#thousands_sep)|Returns a locale-specific element to use as a thousands separator.|  
|[truename](#truename)|Returns a string to use as a text representation of the value `true`.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  numpunct::char_type  
 A type that is used to describe a character used by a locale.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **CharType.**  
  
##  <a name="decimal_point"></a>  numpunct::decimal_point  
 Returns a locale-specific element to use as a decimal point.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific element to use as a decimal point.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_decimal_point](#do_decimal_point).  
  
### <a name="example"></a>Example  
  
```cpp  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="do_decimal_point"></a>  numpunct::do_decimal_point  
 A protected virtual member function that is called to return a locale-specific element to use as a decimal point.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific element to use as a decimal point.  
  
### <a name="example"></a>Example  
  See the example for [decimal_point](#decimal_point), where the virtual member function is called by `decimal_point`.  
  
##  <a name="do_falsename"></a>  numpunct::do_falsename  
 The protected virtual member function returns a sequence to use as a text representation of the value **false**.  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>Return Value  
 A string containing a sequence to use as a text representation of the value **false**.  
  
### <a name="remarks"></a>Remarks  
 The member function returns the string "false" to represent the value **false** in all locales.  
  
### <a name="example"></a>Example  
  See the example for [falsename](#falsename), where the virtual member function is called by `falsename`.  
  
##  <a name="do_grouping"></a>  numpunct::do_grouping  
 A protected virtual member function that is called to return a locale-specific rule for determining how digits are grouped to the left of any decimal point.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific rule for determining how digits are grouped to the left of any decimal point.  
  
### <a name="remarks"></a>Remarks  
 The protected virtual member function returns a locale-specific rule for determining how digits are grouped to the left of any decimal point. The encoding is the same as for **lconv::grouping**.  
  
### <a name="example"></a>Example  
  See the example for [grouping](#grouping), where the virtual member function is called by **grouping**.  
  
##  <a name="do_thousands_sep"></a>  numpunct::do_thousands_sep  
 A protected virtual member function that is called to return a locale-specific element to use as a thousands separator.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Return Value  
 Returns a locale-specific element to use as a thousands separator.  
  
### <a name="remarks"></a>Remarks  
 The protected virtual member function returns a locale-specific element of type **CharType** to use as a group separator to the left of any decimal point.  
  
### <a name="example"></a>Example  
  See the example for [thousands_sep](#thousands_sep), where the virtual member function is called by `thousands_sep`.  
  
##  <a name="do_truename"></a>  numpunct::do_truename  
 A protected virtual member function that is called to return a string to use as a text representation of the value **true**.  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>Remarks  
 A string to use as a text representation of the value **true**.  
  
 All locales return a string "true" to represent the value **true**.  
  
### <a name="example"></a>Example  
  See the example for [truename](#truename), where the virtual member function is called by `truename`.  
  
##  <a name="falsename"></a>  numpunct::falsename  
 Returns a string to use as a text representation of the value **false**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Return Value  
 A string containing a sequence of **CharType**s to use as a text representation of the value **false**.  
  
### <a name="remarks"></a>Remarks  
 The member function returns the string "false" to represent the value **false** in all locales.  
  
 The member function returns [do_falsename](#do_falsename).  
  
### <a name="example"></a>Example  
  
```cpp  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="grouping"></a>  numpunct::grouping  
 Returns a locale-specific rule for determining how digits are grouped to the left of any decimal point.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific rule for determining how digits are grouped to the left of any decimal point.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_grouping](#do_grouping).  
  
### <a name="example"></a>Example  
  
```cpp  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="numpunct"></a>  numpunct::numpunct  
 The constructor for objects of type `numpunct`.  
  
```  
explicit numpunct(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parameters  
 `_Refs`  
 Integer value used to specify the type of memory management for the object.  
  
### <a name="remarks"></a>Remarks  
 The possible values for the `_Refs` parameter and their significance are:  
  
-   0: The lifetime of the object is managed by the locales that contain it.  
  
-   1: The lifetime of the object must be manually managed.  
  
-   \> 1: These values are not defined.  
  
 No direct examples are possible, because the destructor is protected.  
  
 The constructor initializes its base object with **locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="string_type"></a>  numpunct::string_type  
 A type that describes a string containing characters of type **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [basic_string](../standard-library/basic-string-class.md) whose objects can store copies of the punctuation sequences.  
  
##  <a name="thousands_sep"></a>  numpunct::thousands_sep  
 Returns a locale-specific element to use as a thousands separator.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific element to use as a thousands separator.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_thousands_sep](#do_thousands_sep).  
  
### <a name="example"></a>Example  
  
```cpp  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="truename"></a>  numpunct::truename  
 Returns a string to use as a text representation of the value **true**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Return Value  
 A string to use as a text representation of the value **true**.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_truename](#do_truename).  
  
 All locales return a string "true" to represent the value **true**.  
  
### <a name="example"></a>Example  
  
```cpp  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>See Also  
 [\<locale>](../standard-library/locale.md)   
 [facet Class](../standard-library/locale-class.md#facet_class)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)


