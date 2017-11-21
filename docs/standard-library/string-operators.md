---
title: "&lt;string&gt; 運算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- string/std::operator!=
- string/std::operator&gt;
- string/std::operator&gt;&gt;
- string/std::operator&gt;=
- string/std::operator&lt;
- string/std::operator&lt;&lt;
- string/std::operator&lt;=
- string/std::operator+
- string/std::operator==
dev_langs: C++
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
caps.latest.revision: "11"
manager: ghogen
helpviewer_keywords:
- std::operator!= (string)
- std::operator&gt; (string)
- std::operator&gt;&gt; (string)
- std::operator&gt;= (string)
- std::operator&lt; (string)
- std::operator&lt;&lt; (string)
- std::operator&lt;= (string), std::operator== (string)
ms.openlocfilehash: caa6cad7f0801b5459bd2999ae38a3da52c00469
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="ltstringgt-operators"></a>&lt;string&gt; 運算子
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;&gt;](#op_gt_gt)|  
|[operator&gt;=](#op_gt_eq)|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|  
|[operator&lt;=](#op_lt_eq)|[operator+](#op_add)|[operator==](#op_eq_eq)|  
  
##  <a name="op_add"></a>  operator+  
 串連兩個字串物件。  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const CharType right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    CharType right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,  
    const basic_string<CharType, Traits, Allocator>&& right);
```  
  
### <a name="parameters"></a>參數  
 `left`  
 要串連的 C 樣式字串或 `basic_string` 類型物件。  
  
 `right`  
 要串連的 C 樣式字串或 `basic_string` 類型物件。  
  
### <a name="return-value"></a>傳回值  
 輸入字串的串連字串。  
  
### <a name="remarks"></a>備註  
 每個函式都會多載 `operator+`，來串連樣板類別 [basic_string 類別](../standard-library/basic-string-class.md)的兩個物件。 所有函式都會有效地傳回 `basic_string`\< **CharType**, **Traits**, **Allocator**>(_ *Left*). [append](../standard-library/basic-string-class.md#append)(\_ *Right*)。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_con.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // Declaring an object of type basic_string<char>  
   string s1 ( "anti" );  
   string s2 ( "gravity" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "heroine";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // Declaring a character constant  
   char c1 = '!';  
   cout << "The character constant c1 = " << c1 << "." << endl;  
  
   // First member function: concatenates an  object  
   // of type basic_string with an object of type basic_string  
   string s12 = s1 + s2;  
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;  
  
   // Second & fourth member functions: concatenate an object  
   // of type basic_string with an object of C-syle string type  
   string s1s3 = s1 + s3;  
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;  
  
   // Third & fifth member functions: concatenate an object  
   // of type basic_string with a character constant  
   string s1s3c1 = s1s3 + c1;  
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;  
}  
```  
  
```Output  
The basic_string s1 = anti.  
The basic_string s2 = gravity.  
The C-style string s3 = heroine.  
The character constant c1 = !.  
The string concatenating s1 & s2 is: antigravity  
The string concatenating s1 & s3 is: antiheroine  
The string concatenating s1 & s3 is: antiheroine!  
```  
  
##  <a name="op_neq"></a>  operator!=  
 測試運算子左邊的字串物件是否不等於右邊的字串物件。  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left, 
const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>參數  
 `left`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
 `right`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
### <a name="return-value"></a>傳回值  
 如果運算子左邊的 string 物件在詞典編纂上不等於右邊的 string 物件，即為 **true**，否則為 **false**。  
  
### <a name="remarks"></a>備註  
 string 物件之間的比較是以其字元的成對辭典編纂比較為基礎。 如果兩個字串具有相同的字元數，而且其各自的字元值都一樣，則這兩個字串相等。 反之則為不相等。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_ne.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "pluck" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "pluck";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 != s2 )  
      cout << "The strings s1 & s2 are not equal." << endl;  
   else  
      cout << "The strings s1 & s2 are equal." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 != s3 )  
      cout << "The strings s1 & s3 are not equal." << endl;  
   else  
      cout << "The strings s1 & s3 are equal." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s3 != s2 )  
      cout << "The strings s3 & s2 are not equal." << endl;  
   else  
      cout << "The strings s3 & s2 are equal." << endl;  
}  
```  
  
```Output  
The basic_string s1 = pluck.  
The basic_string s2 = strum.  
The C-style string s3 = pluck.  
The strings s1 & s2 are not equal.  
The strings s1 & s3 are equal.  
The strings s3 & s2 are not equal.  
```  
  
##  <a name="op_eq_eq"></a>  operator==  
 測試運算子左邊的字串物件是否等於右邊的字串物件。  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator==(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>參數  
 `left`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
 `right`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
### <a name="return-value"></a>傳回值  
 如果運算子左邊的 string 物件在詞典編纂上等於右邊的 string 物件，即為 **true**，否則為 **false**。  
  
### <a name="remarks"></a>備註  
 string 物件之間的比較是以其字元的成對辭典編纂比較為基礎。 如果兩個字串具有相同的字元數，而且其各自的字元值都一樣，則這兩個字串相等。 反之則為不相等。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_eq.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "pluck" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "pluck";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 == s2 )  
      cout << "The strings s1 & s2 are equal." << endl;  
   else  
      cout << "The strings s1 & s2 are not equal." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 == s3 )  
      cout << "The strings s1 & s3 are equal." << endl;  
   else  
      cout << "The strings s1 & s3 are not equal." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s3 == s2 )  
      cout << "The strings s3 & s2 are equal." << endl;  
   else  
      cout << "The strings s3 & s2 are not equal." << endl;  
}  
```  
  
```Output  
The basic_string s1 = pluck.  
The basic_string s2 = strum.  
The C-style string s3 = pluck.  
The strings s1 & s2 are not equal.  
The strings s1 & s3 are equal.  
The strings s3 & s2 are not equal.  
```  
  
##  <a name="op_lt"></a>  operator&lt;  
 測試運算子左邊的字串物件是否小於右邊的字串物件。  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator<(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>參數  
 `left`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
 `right`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
### <a name="return-value"></a>傳回值  
 如果運算子左邊的 string 物件在詞典編纂上小於右邊的 string 物件，即為 **true**，否則為 **false**。  
  
### <a name="remarks"></a>備註  
 字串間辭典編纂的比較會逐一字元來進行比較，直到符合下列其中一種情況：  
  
-   發現兩個對應的字元不相等，並將其比較的結果做為字串間比較的結果。  
  
-   找不到任何差異，但有一個字串的字元數比另一個字串還多，因而將較短的字串視為小於較長的字串。  
  
-   找不到任何差異，並發現字串具有相同的字串數，因此字串是相等的。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_lt.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "strict";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 < s2 )  
      cout << "The string s1 is less than the string s2." << endl;  
   else  
      cout << "The string s1 is not less than the string s2." << endl;  
  
   // Second member function: comparison between left-hand object  
   // of type basic_string & right-hand object of C-syle string type  
   if ( s1 < s3 )  
      cout << "The string s1 is less than the string s3." << endl;  
   else  
      cout << "The string s1 is not less than the string s3." << endl;  
  
   // Third member function: comparison between left-hand object  
   // of C-syle string type & right-hand object of type basic_string  
   if ( s3 < s2 )  
      cout << "The string s3 is less than the string s2." << endl;  
   else  
      cout << "The string s3 is not less than the string s2." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = strict.  
The string s1 is less than the string s2.  
The string s1 is not less than the string s3.  
The string s3 is less than the string s2.  
```  
  
##  <a name="op_lt_eq"></a>  運算子&lt;=  
 測試運算子左邊的字串物件是否小於或等於右邊的字串物件。  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>參數  
 `left`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
 `right`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
### <a name="return-value"></a>傳回值  
 如果運算子左邊的 string 物件在詞典編纂上小於或等於右邊的 string 物件，即為 **true**，否則為 **false**。  
  
### <a name="remarks"></a>備註  
 字串間辭典編纂的比較會逐一字元來進行比較，直到符合下列其中一種情況：  
  
-   發現兩個對應的字元不相等，並將其比較的結果做為字串間比較的結果。  
  
-   找不到任何差異，但有一個字串的字元數比另一個字串還多，因而將較短的字串視為小於較長的字串。  
  
-   找到相等的字串，並發現字串具有相同的字串數，因此字串是相等的。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_le.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "strict";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 <= s2 )  
      cout << "The string s1 is less than or equal to "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is greater than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 <= s3 )  
      cout << "The string s1 is less than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s1 is greater than "  
           << "the string s3." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type  & right-side object of type basic_string  
   if ( s2 <= s3 )  
      cout << "The string s2 is less than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is greater than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = strict.  
The string s1 is less than or equal to the string s2.  
The string s1 is less than or equal to the string s3.  
The string s2 is greater than the string s3.  
```  
  
##  <a name="op_lt_lt"></a>  運算子&lt;&lt;  
 將字串寫入輸出資料流的樣板函式。  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr, 
    const basic_string<CharType, Traits, Allocator>& str);
```  
  
### <a name="parameters"></a>參數  
 _Ostr  
 要寫入的輸出資料流。  
  
 `str`  
 要輸入至輸出資料流的字串。  
  
### <a name="return-value"></a>傳回值  
 將指定字串的值寫入輸出資料流 `_Ostr`。  
  
### <a name="remarks"></a>備註  
 樣板函式會多載 **operator<<**，以將樣板類別 [basic_string](../standard-library/basic-string-class.md) 的物件 _ *Str* 插入資料流 \_ *Ostr*。 函式會有效地傳回 \_ *Ostr*. **write**( \_ *Str*. [c_str](../standard-library/basic-string-class.md#c_str), \_ *Str*. [size](../standard-library/basic-string-class.md#size))。  
  
##  <a name="op_gt"></a>  運算子&gt;  
 測試運算子左邊的字串物件是否大於右邊的字串物件。  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator>(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>參數  
 `left`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
 `right`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
### <a name="return-value"></a>傳回值  
 如果運算子左邊的 string 物件在詞典編纂上大於右邊的 string 物件，即為 **true**，否則為 **false**。  
  
### <a name="remarks"></a>備註  
 字串間辭典編纂的比較會逐一字元來進行比較，直到符合下列其中一種情況：  
  
-   發現兩個對應的字元不相等，並將其比較的結果做為字串間比較的結果。  
  
-   找不到任何差異，但有一個字串的字元數比另一個字串還多，因而將較短的字串視為小於較長的字串。  
  
-   找不到任何差異，並發現字串具有相同的字串數，因此字串是相等的。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_gt.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "stricture";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 > s2 )  
      cout << "The string s1 is greater than "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is not greater than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s3 > s1 )  
      cout << "The string s3 is greater than "  
           << "the string s1." << endl;  
   else  
      cout << "The string s3 is not greater than "  
           << "the string s1." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s2 > s3 )  
      cout << "The string s2 is greater than "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is not greater than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = stricture.  
The string s1 is not greater than the string s2.  
The string s3 is greater than the string s1.  
The string s2 is greater than the string s3.  
```  
  
##  <a name="op_gt_eq"></a>  運算子&gt;=  
 測試運算子左邊的字串物件是否大於或等於右邊的字串物件。  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>參數  
 `left`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
 `right`  
 要比較的 C 樣式字串或 `basic_string` 類型的物件。  
  
### <a name="return-value"></a>傳回值  
 如果運算子左邊的 string 物件在詞典編纂上大於或等於右邊的 string 物件，即為 **true**，否則為 **false**。  
  
### <a name="remarks"></a>備註  
 字串間辭典編纂的比較會逐一字元來進行比較，直到符合下列其中一種情況：  
  
-   發現兩個對應的字元不相等，並將其比較的結果做為字串間比較的結果。  
  
-   找不到任何差異，但有一個字串的字元數比另一個字串還多，因而將較短的字串視為小於較長的字串。  
  
-   找不到任何差異，並發現字串具有相同的字串數，因此字串是相等的。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_ge.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "stricture";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 >= s2 )  
      cout << "The string s1 is greater than or equal to "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is less than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s3 >= s1 )  
      cout << "The string s3 is greater than or equal to "  
           << "the string s1." << endl;  
   else  
      cout << "The string s3 is less than "  
           << "the string s1." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s2 >= s3 )  
      cout << "The string s2 is greater than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is less than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = stricture.  
The string s1 is less than the string s2.  
The string s3 is greater than or equal to the string s1.  
The string s2 is greater than or equal to the string s3.  
```  
  
##  <a name="op_gt_gt"></a>  運算子&gt;&gt;  
 從輸入資料流讀取字串的樣板函式。  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,  
    basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>參數  
 `_Istr`  
 用來擷取序列的輸入資料流  
  
 `right`  
 要從輸入資料流擷取的字串。  
  
### <a name="return-value"></a>傳回值  
 讀取從指定的字串值`_Istr`並傳回其`right`。  
  
### <a name="remarks"></a>備註  
 除非設定了 `skipws` 旗標，否則運算子會略過開頭的空白字元。 它會讀取後續所有字元，直到下一個字元是空白字元或到達檔案結尾為止。  
  
 樣板函式會多載 **operator>>**，使用擷取自資料流 `_Istr` 的項目序列來取代 `right` 所控制的序列。 擷取停止：  
  
-   到達檔案結尾時。  
  
-   在函式擷取 `_Istr`. **width** 項目之後 (如果該值不為零)。  
  
 在函式擷取 `_Istr`. [max_size](../standard-library/basic-string-class.md#max_size) 項目之後。  
  
-   在函式擷取項目 *ch* 之後 (其 [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **CharType**> >( `getloc`). **is**( **ctype**\< **CharType**>:: **space**, *ch*) 為 true)，會將字元放回去。  
  
 如果函式未擷取任何項目，則會呼叫 [setstate](../standard-library/basic-ios-class.md#setstate)( `ios_base::failbit`)。 在任何情況下，它會呼叫 **istr**. **width**(0)，並傳回 \* **this**。  
  
### <a name="example"></a>範例  
  
```cpp  
// string_op_read_.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   string c0;  
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";  
   cin >> c0;  
   cout << "The string entered is c0 = " << c0 << endl;  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [\<string>](../standard-library/string.md)