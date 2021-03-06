---
title: '&lt;iomanip&gt; 函式'
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::get_money
- iomanip/std::get_time
- iomanip/std::put_money
- iomanip/std::put_time
- iomanip/std::quoted
- iomanip/std::resetiosflags
- iomanip/std::setbase
- iomanip/std::setfill
- iomanip/std::setiosflags
- iomanip/std::setprecision
- iomanip/std::setw
ms.assetid: 3ddde610-70cc-4cfa-8a89-3e83d1d356a8
helpviewer_keywords:
- std::get_money [C++]
- std::get_time [C++]
- std::put_money [C++]
- std::put_time [C++]
- std::quoted [C++]
- std::resetiosflags [C++]
- std::setbase [C++]
- std::setfill [C++]
- std::setiosflags [C++]
- std::setprecision [C++]
- std::setw [C++]
ms.openlocfilehash: 0ed59a94c6b1c7d962b566e2a6b186ffb617a26a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375430"
---
# <a name="ltiomanipgt-functions"></a>&lt;iomanip&gt; 函式

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[參考](#quoted)|[resetiosflags](#resetiosflags)|
|[設定基座](#setbase)|[設定填滿](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="get_money"></a><a name="iomanip_get_money"></a>get_money

使用所需的格式從資料流中擷取貨幣值，並在參數中傳回該值。

```cpp
template <class Money>
T7 get_money(Money& amount, bool use_intl);
```

### <a name="parameters"></a>參數

*量*\
所擷取的貨幣值。

*use_intl*\
如果**為 true,** 請使用國際格式。 預設值為 **false**。

### <a name="remarks"></a>備註

操作器返回`str`一個物件,當從流中提取時,該物件充當調用`formatted input function``get``money_get`與關聯`str`的區域設置面的成員函數的物件,使用*use_intl*來指示國際格式。 如果成功,*調用將儲存*提取的貨幣值。 接著，操作工具會傳回 `str`。

`Money` 必須屬於 `long double` 類型，或是元素及特性參數與 `str` 相同之 `basic_string` 的具現化。

## <a name="get_time"></a><a name="iomanip_get_time"></a>get_time

使用所需的格式從資料流中擷取時間值。 在參數中以時間結構的形式傳回值。

```cpp
template <class Elem>
T10 put_time(struct tm *time_ptr, const Elem *time_format);
```

### <a name="parameters"></a>參數

*time_ptr*\
採用時間結構形式的時間。

*time_format*\
用來取得時間值的所需格式。

### <a name="remarks"></a>備註

操作工具會傳回一個物件，從資料流 `str` 中擷取此物件時，其行為會像`formatted input function`一樣，此函式會呼叫與 `str` 關聯之地區設定 facet `time_get` 的成員函式 `get`，其中會使用 `tptr` 來指出時間結構，以及使用 `fmt` 來指出以 Null 結束之格式字串的開頭。 如果成功，該呼叫就會在時間結構中，儲存與所擷取之任何時間欄位關聯的值。 接著，操作工具會傳回 `str`。

## <a name="put_money"></a><a name="iomanip_put_money"></a>put_money

使用所需的格式將金額插入到資料流中。

```cpp
template <class Money>
T8 put_money(const Money& amount, bool use_intl);
```

### <a name="parameters"></a>參數

*量*\
要插入到資料流中的金額。

*use_intl*\
如果操縱器應使用國際格式,則設置為**true,** 如果不應**使用,則為 false。**

### <a name="return-value"></a>傳回值

傳回 `str`。

### <a name="remarks"></a>備註

操作工具會傳回一個物件，將此物件插入到資料流 `str` 中時，其行為會像已格式化的輸出函式一樣，此函式會呼叫與 `str` 關聯之地區設定 facet `money_put` 的成員函式 `put`。 如果成功,調用將`amount`插入格式適當的,使用*use_intl*來指示國際`str.fill()`格式和,作為填充元素。 接著，操作工具會傳回 `str`。

`Money` 必須屬於 `long double` 類型，或是元素及特性參數與 `str` 相同之 `basic_string` 的具現化。

## <a name="put_time"></a><a name="iomanip_put_time"></a>put_time

使用指定的格式將來自時間結構的時間值寫入到資料流中。

```cpp
template <class Elem>
T10 put_time(struct tm* time_ptr, const Elem* time_format);
```

### <a name="parameters"></a>參數

*time_ptr*\
時間結構中所提供要寫入到資料流中的時間值。

*time_format*\
寫入時間值時所需的格式。

### <a name="remarks"></a>備註

操作工具會傳回一個物件，將此物件插入到資料流 `str` 中時，其行為會像`formatted output function`一樣。 輸出函式會呼叫與 `str` 關聯之地區設定 facet `time_put` 的成員函式 `put`。 輸出函數使用*time_ptr*來指示時間結構和*time_format*來指示 null 終止格式字串的開頭。 如果成功，該呼叫就會插入來自格式字串的常值字串，並轉換來自時間結構的值。 接著，操作工具會傳回 `str`。

## <a name="quoted"></a><a name="quoted"></a>參考

**(C++14 的新功能)** iostream 操作工具，可允許使用 >> 和 << 運算子，將字串便利地往返傳入和傳出資料流。

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>參數

*Str*\
std:字串、字元\*、字串文本或原始字串文本,或其中任何一個(例如,std::wstring,wchar_t)\*的寬版本。

*分隔符*\
使用者指定的字元或寬字元，用作字串開頭和結尾的分隔符號。

*逃脫*\
使用者指定的字元或寬字元，用作字串內逸出序列的逸出字元。

### <a name="remarks"></a>備註

請參閱[使用插入運算子和控制格式](../standard-library/using-insertion-operators-and-controlling-format.md)。

### <a name="example"></a>範例

這個範例將示範如何使用 `quoted` 與預設分隔符號，及使用縮小字串逸出字元。 同樣支援寬字串。

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_quoted_v_nonquoted()
{
    // Results are identical regardless of input string type:
    // string inserted { R"(This is a "sentence".)" }; // raw string literal
    // string inserted { "This is a \"sentence\"." };  // regular string literal
    const char* inserted = "This is a \"sentence\".";  // const char*
    stringstream ss, ss_quoted;
    string extracted, extracted_quoted;

    ss << inserted;
    ss_quoted << quoted(inserted);

    cout << "ss.str() is storing       : " << ss.str() << endl;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl << endl;

    // Round-trip the strings
    ss >> extracted;
    ss_quoted >> quoted(extracted_quoted);

    cout << "After round trip: " << endl;
    cout << "Non-quoted      : " << extracted << endl;
    cout << "Quoted          : " << extracted_quoted << endl;
}

int main(int argc, char* argv[])
{
    show_quoted_v_nonquoted();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}

/* Output:
ss.str() is storing       : This is a "sentence".
ss_quoted.str() is storing: "This is a \"sentence\"."

After round trip:
Non-quoted      : This
Quoted          : This is a "sentence".

Press Enter to exit
*/
```

### <a name="example"></a>範例

下列範例將示範如何提供分隔符號和/或逸出字元給自訂：

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_custom_delimiter()
{
    string inserted{ R"("This" "is" "a" "heavily-quoted" "sentence".)" };
    // string inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    // const char* inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    stringstream ss, ss_quoted;
    string extracted;

    ss_quoted << quoted(inserted, '*');
    ss << inserted;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl;
    cout << "ss.str() is storing       : " << ss.str() << endl << endl;

    // Use the same quoted arguments as on insertion.
    ss_quoted >> quoted(extracted, '*');

    cout << "After round trip: " << endl;
    cout << "Quoted          : " << extracted << endl;

    extracted = {};
    ss >> extracted;
    cout << "Non-quoted      : " << extracted << endl << endl;
}

void show_custom_escape()
{
    string inserted{ R"(\\root\trunk\branch\nest\egg\yolk)" };
    // string inserted{ "\\\\root\\trunk\\branch\\nest\\egg\\yolk" };
    stringstream ss, ss_quoted, ss_quoted_custom;
    string extracted;

    // Use '"' as delimiter and '~' as escape character.
    ss_quoted_custom << quoted(inserted, '"', '~');
    ss_quoted << quoted(inserted);
    ss << inserted;
    cout << "ss_quoted_custom.str(): " << ss_quoted_custom.str() << endl;
    cout << "ss_quoted.str()       : " << ss_quoted.str() << endl;
    cout << "ss.str()              : " << ss.str() << endl << endl;

    // No spaces in this string, so non-quoted behaves same as quoted
    // after round-tripping.
}

int main(int argc, char* argv[])
{
    cout << "Custom delimiter:" << endl;
    show_custom_delimiter();
    cout << "Custom escape character:" << endl;
    show_custom_escape();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}
/* Output:
Custom delimiter:
ss_quoted.str() is storing: *"This" "is" "a" "heavily-quoted" "sentence".*
ss.str() is storing       : "This" "is" "a" "heavily-quoted" "sentence".

After round trip:
Quoted          : "This" "is" "a" "heavily-quoted" "sentence".
Non-quoted      : "This"

Custom escape character:
ss_quoted_custom.str(): "\\root\trunk\branch\nest\egg\yolk"
ss_quoted.str()       : "\\\\root\\trunk\\branch\\nest\\egg\\yolk"
ss.str()              : \\root\trunk\branch\nest\egg\yolk

Press Enter to exit
*/
```

## <a name="resetiosflags"></a><a name="resetiosflags"></a>重置標誌

清除指定的旗標。

```cpp
T1 resetiosflags(ios_base::fmtflags mask);
```

### <a name="parameters"></a>參數

*面具*\
要清除的旗標。

### <a name="return-value"></a>傳回值

操作`str`器傳回物件,當從 串流中提取或插入到流中時,呼`str.`叫[setf](../standard-library/ios-base-class.md#setf)`(ios_base::`[fmtflags,](../standard-library/ios-base-class.md#fmtflags)`, mask)`然後`str`傳回 。

### <a name="example"></a>範例

如需使用 `resetiosflags` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。

## <a name="setbase"></a><a name="setbase"></a>設定基座

設定整數的基底。

```cpp
T3 setbase(int base);
```

### <a name="parameters"></a>參數

*基地*\
數字基底。

### <a name="return-value"></a>傳回值

操作器傳回物件,當從流中提取或插入到流`str`中時,該`str.setf(mask,`物件呼叫[ios_base::基場](../standard-library/ios-base-class.md#fmtflags)`)``str`,然後返回 。 此處`mask`,確定如下:

- 如果*基數*為`mask`8, 則`ios_base::`為[10 。](../standard-library/ios-functions.md#oct)

- 如果*基為*10,`ios_base::`則遮罩為[de](../standard-library/ios-functions.md#dec)。

- 如果*基為*16,`mask`則`ios_base::`為[十六進制](../standard-library/ios-functions.md#hex)。

- 如果*基*是任何其他值,則遮罩為`ios_base::` [fmtflags](../standard-library/ios-base-class.md#fmtflags)`(0)`。

### <a name="example"></a>範例

如需使用 `setbase` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。

## <a name="setfill"></a><a name="setfill"></a>設定填滿

設定將用來填滿靠右對齊顯示中的空格字元。

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>參數

*Ch*\
將用來填滿靠右對齊顯示中空格的字元。

### <a name="return-value"></a>傳回值

樣本操作器傳回物件,當從流中提取或插入到流`str`中時,呼叫`str.`[填充](../standard-library/basic-ios-class.md#fill)`(Ch)`,然後傳`str`回 。 類型`Elem`必須與`str`流的元素類型相同。

### <a name="example"></a>範例

如需使用 `setfill` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。

## <a name="setiosflags"></a><a name="setiosflags"></a>設定旗標

設定指定的旗標。

```cpp
T2 setiosflags(ios_base::fmtflags mask);
```

### <a name="parameters"></a>參數

*面具*\
要設定的旗標。

### <a name="return-value"></a>傳回值

操作器傳回物件,當從流中提取或插入到流`str`中時,呼叫`str.` [setf,](../standard-library/ios-base-class.md#setf)`(mask)``str`然後傳回 。

### <a name="example"></a>範例

如需使用 `setiosflags` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。

## <a name="setprecision"></a><a name="setprecision"></a>設定精確度

設定浮點值的有效位數。

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>參數

*普雷克*\
浮點數值的有效位數。

### <a name="return-value"></a>傳回值

操作`str`器傳回物件,當從流中提取或插入到流中時,呼叫`str.`[精度](../standard-library/ios-base-class.md#precision)`(Prec)`,然後傳`str`回 。

### <a name="example"></a>範例

如需使用 `setprecision` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。

## <a name="setw"></a><a name="setw"></a>塞特瓦

指定資料流中下一個元素的顯示欄位寬度。

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>參數

*寬*\
顯示欄位的寬度。

### <a name="return-value"></a>傳回值

操作`str`器傳回物件,當從流中提取或插入到流中時,呼叫`str.`[寬度](../standard-library/ios-base-class.md#width)`(Wide)`,然後傳回`str`。

### <a name="remarks"></a>備註

setw 只會設定資料流中下一個元素的寬度，而且必須插入在您想要為其指定寬度的每個元素前面。

### <a name="example"></a>範例

```cpp
// iomanip_setw.cpp
// compile with: /EHsc
// Defines the entry point for the console application.
//
// Sample use of the following manipulators:
//   resetiosflags
//   setiosflags
//   setbase
//   setfill
//   setprecision
//   setw

#include <iostream>
#include <iomanip>

using namespace std;

const double   d1 = 1.23456789;
const double   d2 = 12.3456789;
const double   d3 = 123.456789;
const double   d4 = 1234.56789;
const double   d5 = 12345.6789;
const long      l1 = 16;
const long      l2 = 256;
const long      l3 = 1024;
const long      l4 = 4096;
const long      l5 = 65536;
int         base = 10;

void DisplayDefault( )
{
   cout << endl << "default display" << endl;
   cout << "d1 = " << d1 << endl;
   cout << "d2 = " << d2 << endl;
   cout << "d3 = " << d3 << endl;
   cout << "d4 = " << d4 << endl;
   cout << "d5 = " << d5 << endl;
}

void DisplayWidth( int n )
{
   cout << endl << "fixed width display set to " << n << ".\n";
   cout << "d1 = " << setw(n) << d1 << endl;
   cout << "d2 = " << setw(n) << d2 << endl;
   cout << "d3 = " << setw(n) << d3 << endl;
   cout << "d4 = " << setw(n) << d4 << endl;
   cout << "d5 = " << setw(n) << d5 << endl;
}

void DisplayLongs( )
{
   cout << setbase(10);
   cout << endl << "setbase(" << base << ")" << endl;
   cout << setbase(base);
   cout << "l1 = " << l1 << endl;
   cout << "l2 = " << l2 << endl;
   cout << "l3 = " << l3 << endl;
   cout << "l4 = " << l4 << endl;
   cout << "l5 = " << l5 << endl;
}

int main( int argc, char* argv[] )
{
   DisplayDefault( );

   cout << endl << "setprecision(" << 3 << ")" << setprecision(3);
   DisplayDefault( );

   cout << endl << "setprecision(" << 12 << ")" << setprecision(12);
   DisplayDefault( );

   cout << setiosflags(ios_base::scientific);
   cout << endl << "setiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << resetiosflags(ios_base::scientific);
   cout << endl << "resetiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << endl << "setfill('" << 'S' << "')" << setfill('S');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setfill('" << ' ' << "')" << setfill(' ');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setprecision(" << 8 << ")" << setprecision(8);
   DisplayWidth(10);
   DisplayDefault( );

   base = 16;
   DisplayLongs( );

   base = 8;
   DisplayLongs( );

   base = 10;
   DisplayLongs( );

   return   0;
}
```

```Output

default display
d1 = 1.23457
d2 = 12.3457
d3 = 123.457
d4 = 1234.57
d5 = 12345.7

setprecision(3)
default display
d1 = 1.23
d2 = 12.3
d3 = 123
d4 = 1.23e+003
d5 = 1.23e+004

setprecision(12)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setiosflags(4096)
default display
d1 = 1.234567890000e+000
d2 = 1.234567890000e+001
d3 = 1.234567890000e+002
d4 = 1.234567890000e+003
d5 = 1.234567890000e+004

resetiosflags(4096)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill('S')
fixed width display set to 15.
d1 = SSSSS1.23456789
d2 = SSSSS12.3456789
d3 = SSSSS123.456789
d4 = SSSSS1234.56789
d5 = SSSSS12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill(' ')
fixed width display set to 15.
d1 =      1.23456789
d2 =      12.3456789
d3 =      123.456789
d4 =      1234.56789
d5 =      12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setprecision(8)
fixed width display set to 10.
d1 =  1.2345679
d2 =  12.345679
d3 =  123.45679
d4 =  1234.5679
d5 =  12345.679

default display
d1 = 1.2345679
d2 = 12.345679
d3 = 123.45679
d4 = 1234.5679
d5 = 12345.679

setbase(16)
l1 = 10
l2 = 100
l3 = 400
l4 = 1000
l5 = 10000

setbase(8)
l1 = 20
l2 = 400
l3 = 2000
l4 = 10000
l5 = 200000

setbase(10)
l1 = 16
l2 = 256
l3 = 1024
l4 = 4096
l5 = 65536
```

## <a name="see-also"></a>另請參閱

[\<奧馬尼普>](../standard-library/iomanip.md)
