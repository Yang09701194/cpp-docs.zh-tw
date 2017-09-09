---
title: moneypunct Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/std::moneypunct
- locale/std::moneypunct::char_type
- locale/std::moneypunct::string_type
- locale/std::moneypunct::curr_symbol
- locale/std::moneypunct::decimal_point
- locale/std::moneypunct::do_curr_symbol
- locale/std::moneypunct::do_decimal_point
- locale/std::moneypunct::do_frac_digits
- locale/std::moneypunct::do_grouping
- locale/std::moneypunct::do_neg_format
- locale/std::moneypunct::do_negative_sign
- locale/std::moneypunct::do_pos_format
- locale/std::moneypunct::do_positive_sign
- locale/std::moneypunct::do_thousands_sep
- locale/std::moneypunct::frac_digits
- locale/std::moneypunct::grouping
- locale/std::moneypunct::neg_format
- locale/std::moneypunct::negative_sign
- locale/std::moneypunct::pos_format
- locale/std::moneypunct::positive_sign
- locale/std::moneypunct::thousands_sep
dev_langs:
- C++
helpviewer_keywords:
- std::moneypunct [C++]
- std::moneypunct [C++], char_type
- std::moneypunct [C++], string_type
- std::moneypunct [C++], curr_symbol
- std::moneypunct [C++], decimal_point
- std::moneypunct [C++], do_curr_symbol
- std::moneypunct [C++], do_decimal_point
- std::moneypunct [C++], do_frac_digits
- std::moneypunct [C++], do_grouping
- std::moneypunct [C++], do_neg_format
- std::moneypunct [C++], do_negative_sign
- std::moneypunct [C++], do_pos_format
- std::moneypunct [C++], do_positive_sign
- std::moneypunct [C++], do_thousands_sep
- std::moneypunct [C++], frac_digits
- std::moneypunct [C++], grouping
- std::moneypunct [C++], neg_format
- std::moneypunct [C++], negative_sign
- std::moneypunct [C++], pos_format
- std::moneypunct [C++], positive_sign
- std::moneypunct [C++], thousands_sep
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
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
ms.openlocfilehash: 6d93d1577734d8ae8ec3211218108474de329635
ms.contentlocale: zh-tw
ms.lasthandoff: 09/09/2017

---
# <a name="moneypunct-class"></a>moneypunct Class
The template class describes an object that can serve as a locale facet to describe the sequences of type `CharType` used to represent a monetary input field or a monetary output field. If the template parameter `Intl` is `true`, international conventions are observed.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType, bool Intl>  
class moneypunct;  
```  
  
#### <a name="parameters"></a>Parameters  
 `CharType`  
 The type used within a program to encode characters.  
  
 `Intl`  
 A flag specifying whether international conventions are to be observed.  
  
## <a name="remarks"></a>Remarks  
 As with any locale facet, the static object ID has an initial stored value of zero. The first attempt to access its stored value stores a unique positive value in **id.**  
  
 The const static object intl stores the value of the template parameter **Intl**.  
  
### <a name="constructors"></a>Constructors  
  
|||  
|-|-|  
|[moneypunct](#moneypunct)|Constructor of objects of type `moneypunct`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|A type that is used to describe a character used by a locale.|  
|[string_type](#string_type)|A type that describes a string containing characters of type `CharType`.|  
  
### <a name="member-functions"></a>Member Functions  
  
|||  
|-|-|  
|[curr_symbol](#curr_symbol)|Returns a locale-specific sequence of elements to use as a currency symbol.|  
|[decimal_point](#decimal_point)|Returns a locale-specific sequence of elements to use as a decimal point symbol.|  
|[do_curr_symbol](#do_curr_symbol)|A protected virtual member function that returns a locale-specific sequence of elements to use as a currency symbol.|  
|[do_decimal_point](#do_decimal_point)|A protected virtual member function that is called to return a locale-specific sequence of elements to use as a decimal point symbol.|  
|[do_frac_digits](#do_frac_digits)|The protected virtual member function returns a locale-specific count of the number of digits to display to the right of any decimal point.|  
|[do_grouping](#do_grouping)|The protected virtual member function returns a locale-specific rule for determining how digits are grouped to the left of any decimal point.|  
|[do_neg_format](#do_neg_format)|A protected virtual member function that is called to return a locale-specific rule for formatting outputs with negative amounts.|  
|[do_negative_sign](#do_negative_sign)|A protected virtual member function that is called to return a locale-specific sequence of elements to use as a negative sign symbol.|  
|[do_pos_format](#do_pos_format)|A protected virtual member function that is called to return a locale-specific rule for formatting outputs with positive amounts.|  
|[do_positive_sign](#do_positive_sign)|A protected virtual member function that is called to return a locale-specific sequence of elements to use as a positive sign symbol.|  
|[do_thousands_sep](#do_thousands_sep)|A protected virtual member function that is called to return a locale-specific sequence of elements to use as a thousands separator symbol.|  
|[frac_digits](#frac_digits)|Returns a locale-specific count of the number of digits to display to the right of any decimal point.|  
|[grouping](#grouping)|Returns a locale-specific rule for determining how digits are grouped to the left of any decimal point.|  
|[neg_format](#neg_format)|Returns a locale-specific rule for formatting outputs with negative amounts.|  
|[negative_sign](#negative_sign)|Returns a locale-specific sequence of elements to use as a negative sign symbol.|  
|[pos_format](#pos_format)|Returns a locale-specific rule for formatting outputs with positive amounts.|  
|[positive_sign](#positive_sign)|Returns a locale-specific sequence of elements to use as a positive sign symbol.|  
|[thousands_sep](#thousands_sep)|Returns a locale-specific sequence of elements to use as a thousands separator symbol.|  
  
## <a name="requirements"></a>Requirements  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  moneypunct::char_type  
 A type that is used to describe a character used by a locale.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Remarks  
 The type is a synonym for the template parameter **CharType**.  
  
##  <a name="curr_symbol"></a>  moneypunct::curr_symbol  
 Returns a locale-specific sequence of elements to use as a currency symbol.  
  
```  
string_type curr_symbol() const;
```  
  
### <a name="return-value"></a>Return Value  
 A string containing the currency symbol.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_curr_symbol](#do_curr_symbol).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_curr_symbol.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct < char, true > &mpunct = use_facet < moneypunct < char, true > >(loc);  
   cout << loc.name( ) << " international currency symbol "<<  mpunct.curr_symbol( ) << endl;  
  
   const moneypunct < char, false> &mpunct2 = use_facet < moneypunct < char, false> >(loc);  
   cout << loc.name( ) << " domestic currency symbol "<<  mpunct2.curr_symbol( ) << endl;  
};  
```  
  
##  <a name="decimal_point"></a>  moneypunct::decimal_point  
 Returns a locale-specific sequence of elements to use as a decimal point symbol.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific sequence of elements to use as a decimal point symbol.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_decimal_point](#do_decimal_point).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_decimal_pt.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc("german_germany");  
  
   const moneypunct < char, true > &mpunct = use_facet   
      < moneypunct < char, true > >(loc);  
   cout << loc.name( ) << " international decimal point "  
        << mpunct.decimal_point( ) << endl;  
  
   const moneypunct < char, false> &mpunct2 = use_facet   
      < moneypunct < char, false> >(loc);  
   cout << loc.name( ) << " domestic decimal point "  
        << mpunct2.decimal_point( ) << endl;  
}  
```  
  
```Output  
German_Germany.1252 international decimal point ,  
German_Germany.1252 domestic decimal point ,  
```  
  
##  <a name="do_curr_symbol"></a>  moneypunct::do_curr_symbol  
 A protected virtual member function that returns a locale-specific sequence of elements to use as a currency symbol.  
  
```  
virtual string_type do_curr_symbol() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific sequence of elements to use as a decimal point symbol.  
  
### <a name="example"></a>Example  
  See the example for [curr_symbol](#curr_symbol), where the virtual member function is called by `curr_symbol`.  
  
##  <a name="do_decimal_point"></a>  moneypunct::do_decimal_point  
 A protected virtual member function that returns a locale-specific sequence of elements to use as a decimal point symbol.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific sequence of elements to use as a decimal point symbol.  
  
### <a name="example"></a>Example  
  See the example for [decimal_point](#decimal_point), where the virtual member function is called by `decimal_point`.  
  
##  <a name="do_frac_digits"></a>  moneypunct::do_frac_digits  
 A protected virtual member function that returns a locale-specific count of the number of digits to display to the right of any decimal point.  
  
```  
virtual int do_frac_digits() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific count of the number of digits to display to the right of any decimal point.  
  
### <a name="example"></a>Example  
  See the example for [frac_digits](#frac_digits), where the virtual member function is called by `frac_digits`.  
  
##  <a name="do_grouping"></a>  moneypunct::do_grouping  
 A protected virtual member function that returns a locale-specific rule for determining how digits are grouped to the left of any decimal point.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific rule for determining how digits are grouped to the left of any decimal point.  
  
### <a name="example"></a>Example  
  See the example for [grouping](#grouping), where the virtual member function is called by **grouping**.  
  
##  <a name="do_neg_format"></a>  moneypunct::do_neg_format  
 A protected virtual member function that is called to return a locale-specific rule for formatting outputs with negative amounts.  
  
```  
virtual pattern do_neg_format() const;
```  
  
### <a name="return-value"></a>Return Value  
 The protected virtual member function returns a locale-specific rule for determining how to generate a monetary output field for a negative amount. Each of the four elements of **pattern::field** can have the values:  
  
- **none** to match zero or more spaces or generate nothing.  
  
- **sign** to match or generate a positive or negative sign.  
  
- **space** to match zero or more spaces or generate a space.  
  
- **symbol** to match or generate a currency symbol.  
  
- **value** to match or generate a monetary value.  
  
 Components of a monetary output field are generated and components of a monetary input field are matched in the order in which these elements appear in **pattern::field**. Each of the values **sign**, **symbol**, **value**, and either **none** or **space** must appear exactly once. The value **none** must not appear first. The value space **must** not appear first or last. If **Intl** is true, the order is **symbol**, **sign**, **none**, then **value**.  
  
 The template version of `moneypunct`\< **CharType**, **Intl**> returns `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.  
  
### <a name="example"></a>Example  
  See the example for [neg_format](#neg_format), where the virtual member function is called by `neg_format`.  
  
##  <a name="do_negative_sign"></a>  moneypunct::do_negative_sign  
 A protected virtual member function that is called to return a locale-specific sequence of elements to use as a negative sign symbol.  
  
```  
virtual string_type do_negative_sign() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific sequence of elements to use as a negative sign.  
  
### <a name="example"></a>Example  
  See the example for [negative_sign](#negative_sign), where the virtual member function is called by `negative_sign`.  
  
##  <a name="do_pos_format"></a>  moneypunct::do_pos_format  
 A protected virtual member function that is called to return a locale-specific rule for formatting outputs with positive amounts.  
  
```  
virtual pattern do_pos_format() const;
```  
  
### <a name="return-value"></a>Return Value  
 The protected virtual member function returns a locale-specific rule for determining how to generate a monetary output field for a positive amount. (It also determines how to match the components of a monetary input field.) The encoding is the same as for [do_neg_format](#do_neg_format).  
  
 The template version of moneypunct\< **CharType**, **Inputlterator**> returns `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.  
  
### <a name="example"></a>Example  
  See the example for [pos_format](#pos_format), where the virtual member function is called by `pos_format`.  
  
##  <a name="do_positive_sign"></a>  moneypunct::do_positive_sign  
 A protected virtual member function that returns a locale-specific sequence of elements to use as a positive sign.  
  
```  
virtual string_type do_positive_sign() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific sequence of elements to use as a positive sign.  
  
### <a name="example"></a>Example  
  See the example for [positive_sign](#positive_sign), where the virtual member function is called by `positive_sign`.  
  
##  <a name="do_thousands_sep"></a>  moneypunct::do_thousands_sep  
 A protected virtual member function that returns a locale-specific element to use as a group separator to the left of any decimal point.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific element to use as a group separator to the left of any decimal point.  
  
### <a name="example"></a>Example  
  See the example for [thousands_sep](#thousands_sep), where the virtual member function is called by `thousands_sep`.  
  
##  <a name="frac_digits"></a>  moneypunct::frac_digits  
 Returns a locale-specific count of the number of digits to display to the right of any decimal point.  
  
```  
int frac_digits() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific count of the number of digits to display to the right of any decimal point.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_frac_digits](#do_frac_digits).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_frac_digits.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true> >(loc);  
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " international frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct.frac_digits ( ) << endl << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
       use_facet <moneypunct <char, false> >(loc);  
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " domestic grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct2.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " domestic frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct2.frac_digits ( ) << endl << endl;  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 international frac_digits  
 to the right of the radix character: 2  
  
German_Germany.1252 domestic grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 domestic frac_digits  
 to the right of the radix character: 2  
```  
  
##  <a name="grouping"></a>  moneypunct::grouping  
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
// moneypunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true> >( loc );  
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " international frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct.frac_digits ( ) << endl << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
       use_facet <moneypunct <char, false> >( loc );  
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " domestic grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct2.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " domestic frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct2.frac_digits ( ) << endl << endl;  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 international frac_digits  
 to the right of the radix character: 2  
  
German_Germany.1252 domestic grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 domestic frac_digits  
 to the right of the radix character: 2  
```  
  
##  <a name="moneypunct"></a>  moneypunct::moneypunct  
 Constructor of objects of type `moneypunct`.  
  
```  
explicit moneypunct(size_t _Refs = 0);
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
  
 The constructor initializes its base object with [locale::facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).  
  
##  <a name="neg_format"></a>  moneypunct::neg_format  
 Returns a locale-specific rule for formatting outputs with negative amounts.  
  
```  
pattern neg_format() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific rule for formatting outputs with negative amounts.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_neg_format](#do_neg_format).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_neg_format.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( ) {  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international negative number format: "  
        << mpunct.neg_format( ).field[0]   
        << mpunct.neg_format( ).field[1]   
        << mpunct.neg_format( ).field[2]   
        << mpunct.neg_format( ).field[3] << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic negative number format: "  
        << mpunct2.neg_format( ).field[0]   
        << mpunct2.neg_format( ).field[1]   
        << mpunct2.neg_format( ).field[2]   
        << mpunct2.neg_format( ).field[3] << endl;  
}  
```  
  
##  <a name="negative_sign"></a>  moneypunct::negative_sign  
 Returns a locale-specific sequence of elements to use as a negative sign symbol.  
  
```  
string_type negative_sign() const;
```  
  
### <a name="return-value"></a>Return Value  
 Returns a locale-specific sequence of elements to use as a negative sign symbol.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_negative_sign](#do_negative_sign).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_neg_sign.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true> >(loc);  
   cout << loc.name( ) << " international negative sign: "  
        << mpunct.negative_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic negative sign: "  
        << mpunct2.negative_sign( ) << endl;  
  
   locale loc2( "French" );  
  
   const moneypunct <char, true> &mpunct3 =   
      use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international negative sign: "  
        << mpunct3.negative_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic negative sign: "  
        << mpunct4.negative_sign( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 international negative sign: -  
German_Germany.1252 domestic negative sign: -  
French_France.1252 international negative sign: -  
French_France.1252 domestic negative sign: -  
```  
  
##  <a name="pos_format"></a>  moneypunct::pos_format  
 Returns a locale-specific rule for formatting outputs with positive amounts.  
  
```  
pattern pos_format() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific rule for formatting outputs with positive amounts.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_pos_format](#do_pos_format).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_pos_format.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main() {  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true> >(loc);  
   cout << loc.name( ) << " international positive number format: "  
        << mpunct.pos_format( ).field[0]   
        << mpunct.pos_format( ).field[1]   
        << mpunct.pos_format( ).field[2]   
        << mpunct.pos_format( ).field[3] << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic positive number format: "  
        << mpunct2.pos_format( ).field[0]   
        << mpunct2.pos_format( ).field[1]   
        << mpunct2.pos_format( ).field[2]   
        << mpunct2.pos_format( ).field[3] << endl;  
}  
```  
  
##  <a name="positive_sign"></a>  moneypunct::positive_sign  
 Returns a locale-specific sequence of elements to use as a positive sign symbol.  
  
```  
string_type positive_sign() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific sequence of elements to use as a positive sign symbol.  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_positive_sign](#do_positive_sign).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_pos_sign.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international positive sign:"  
        << mpunct.positive_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic positive sign:"  
        << mpunct2.positive_sign( ) << endl;  
  
   locale loc2( "French" );  
  
   const moneypunct <char, true> &mpunct3 =   
      use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international positive sign:"  
        << mpunct3.positive_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic positive sign:"  
        << mpunct4.positive_sign( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 international positive sign:  
German_Germany.1252 domestic positive sign:  
French_France.1252 international positive sign:  
French_France.1252 domestic positive sign:  
```  
  
##  <a name="string_type"></a>  moneypunct::string_type  
 A type that describes a string containing characters of type **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Remarks  
 The type describes a specialization of template class [basic_string](../standard-library/basic-string-class.md) whose objects can store copies of the punctuation sequences.  
  
##  <a name="thousands_sep"></a>  moneypunct::thousands_sep  
 Returns a locale-specific sequence of elements to use as a thousands separator symbol.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Return Value  
 A locale-specific sequence of elements to use as a thousands separator  
  
### <a name="remarks"></a>Remarks  
 The member function returns [do_thousands_sep](#do_thousands_sep).  
  
### <a name="example"></a>Example  
  
```cpp  
// moneypunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international thousands separator: "  
        << mpunct.thousands_sep( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic thousands separator: "  
        << mpunct2.thousands_sep( ) << endl << endl;  
  
   locale loc2( "english_canada" );  
  
   const moneypunct <char, true> &mpunct3 =   
       use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international thousands separator: "  
        << mpunct3.thousands_sep( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic thousands separator: "  
        << mpunct4.thousands_sep( ) << endl;  
}  
```  
  
```Output  
German_Germany.1252 international thousands separator: .  
German_Germany.1252 domestic thousands separator: .  
  
English_Canada.1252 international thousands separator: ,  
English_Canada.1252 domestic thousands separator: ,  
```  
  
## <a name="see-also"></a>See Also  
 [\<locale>](../standard-library/locale.md)   
 [Thread Safety in the C++ Standard Library](../standard-library/thread-safety-in-the-cpp-standard-library.md)


