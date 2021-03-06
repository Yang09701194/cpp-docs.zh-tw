---
title: ostreambuf_iterator 類別
ms.date: 11/04/2016
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
ms.openlocfilehash: 8e9fa10888b511ad2a500f64faf610dc7dd5ba03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373568"
---
# <a name="ostreambuf_iterator-class"></a>ostreambuf_iterator 類別

類ostreambuf_iterator範描述一個輸出反覆運算器物件,該物件使用提取**運算元>>** 將連續字元元素寫入輸出流。 `ostreambuf_iterator` 與 [ostream_iterator 類別](../standard-library/ostream-iterator-class.md)的不同處在於字元 (而非泛型類型) 做為要插入至輸出資料流的物件類型。

## <a name="syntax"></a>語法

```cpp
template <class CharType = char class Traits = char_traits <CharType>>
```

### <a name="parameters"></a>參數

*字元類型*\
類型，表示 ostreambuf_iterator 的字元類型。 這裡參數是選擇的預設值為**char**。

*性狀*\
類型，表示 ostreambuf_iterator 的字元類型。 這個引數是選用引數，且預設值是 `char_traits`\< *CharType>*。

## <a name="remarks"></a>備註

ostreambuf_iterator 類別必須符合輸出迭代器的需求。 使用 `ostreambuf_iterator`，演算法可以直接寫入輸出資料流。 此類別提供低階資料流迭代器，允許存取字元格式的原始 (未格式化) I/O 資料流，也能夠略過與進階資料流迭代器相關聯的緩衝和字元轉譯。

### <a name="constructors"></a>建構函式

|建構函式|描述|
|-|-|
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|建構 `ostreambuf_iterator`，初始化以將字元寫入輸出資料流中。|

### <a name="typedefs"></a>Typedefs

|類型名稱|描述|
|-|-|
|[char_type](#char_type)|類型，提供 `ostreambuf_iterator` 的字元類型。|
|[ostream_type](#ostreambuf_iterator_ostream_type)|類型，提供 `ostream_iterator` 的資料流類型。|
|[streambuf_type](#streambuf_type)|類型，提供 `ostreambuf_iterator` 的資料流類型。|
|[traits_type](#traits_type)|類型，提供 `ostream_iterator` 的字元特性類型。|

### <a name="member-functions"></a>成員函數

|成員函數|描述|
|-|-|
|[失敗](#failed)|測試插入至輸出資料流緩衝區是否失敗。|

### <a name="operators"></a>操作員

|運算子|描述|
|-|-|
|[運算子*](#op_star)|\*`i` = 用於實現`x`輸出反覆運算器表達式的取消引用運算符。|
|[運算子*](#op_add_add)|無作用的遞增運算子，傳回 `ostreambuf_iterator`，指向在呼叫作業之前它所定址的相同物件。|
|[運算子*](#op_eq)|此運算子會將字元插入至相關聯的資料流緩衝區。|

## <a name="requirements"></a>需求

**標頭：** \<iterator>

**命名空間：** std

## <a name="ostreambuf_iteratorchar_type"></a><a name="char_type"></a>ostreambuf_iterator:char_type

類型，提供 `ostreambuf_iterator` 的字元類型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>備註

此類型是樣板參數 `CharType` 的同義字。

### <a name="example"></a>範例

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
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="ostreambuf_iteratorfailed"></a><a name="failed"></a>ostreambuf_iterator:失敗

測試插入至輸出資料流緩衝區是否失敗。

```cpp
bool failed() const throw();
```

### <a name="return-value"></a>傳回值

如果之前插入至輸出資料流緩衝區沒有失敗，則為 **true**；否則為 **false**。

### <a name="remarks"></a>備註

如果任何之前使用成員 `operator=` 呼叫 **subf**_-> `sputc` 傳回了 **eof**，成員函式會傳回 **true**。

### <a name="example"></a>範例

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
/* Output:
abc are characters output individually.
No insertions failed.
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_star"></a>ostreambuf_iterator::操作員\*

用於實現輸出反覆運算\*器運算式 i *x* = *x*的非功能取消參考運算符。

```cpp
ostreambuf_iterator<CharType, Traits>& operator*();
```

### <a name="return-value"></a>傳回值

ostreambuf 迭代器物件。

### <a name="remarks"></a>備註

此運算碼僅\*在輸出反覆運算器表示式*i* = *x*中函數,以輸出字元以流式傳輸緩衝區。 應用於 ostreambuf 反覆運算器,它返回反覆運算器;iter返回**iter,** ** \* **

### <a name="example"></a>範例

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
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_add_add"></a>ostreambuf_iterator::操作員*

無作用的遞增運算子，傳回 ostream 迭代器，指向在呼叫作業之前它所定址的相同字元。

```cpp
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```

### <a name="return-value"></a>傳回值

針對原先定址的字元，或是轉換為 `ostreambuf_iterator`\< **CharType**, **Traits**> 之實作定義物件的參考。

### <a name="remarks"></a>備註

運算子用於匯出影像\*的影像表示式*i* = *x*。

### <a name="example"></a>範例

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
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratoroperator"></a><a name="op_eq"></a>ostreambuf_iterator::操作員*

此運算子會將字元插入至相關聯的資料流緩衝區。

```cpp
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```

### <a name="parameters"></a>參數

*_Char*\
要插入至資料流緩衝區的字元。

### <a name="return-value"></a>傳回值

插入至資料流緩衝區的字元參考。

### <a name="remarks"></a>備註

用於實現輸出\*反覆運算器運算*式 i* = *x*的賦值運算符,用於寫入輸出流。

### <a name="example"></a>範例

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
/* Output:
Elements written to output stream:
OUT
*/
```

## <a name="ostreambuf_iteratorostreambuf_iterator"></a><a name="ostreambuf_iterator_ostreambuf_iterator"></a>ostreambuf_iterator:ostreambuf_iterator

建構 `ostreambuf_iterator`，初始化以將字元寫入輸出資料流中。

```cpp
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```

### <a name="parameters"></a>參數

*斯特布夫*\
用於初始化輸出資料流緩衝區指標的輸出 streambuf 物件。

*奧斯特*\
用於初始化輸出資料流緩衝區指標的輸出資料流物件。

### <a name="remarks"></a>備註

第一個建構函數用*strbuf*初始化輸出流緩衝區指標。

第二個建構函式會使用 `Ostr` 初始化輸出資料流緩衝區指標。 `rdbuf`. 儲存的指標不能是 null 指標。

### <a name="example"></a>範例

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
/* Output:
OUT are characters output individually.
These characters are being written to the output stream.
*/
```

## <a name="ostreambuf_iteratorostream_type"></a><a name="ostreambuf_iterator_ostream_type"></a>ostreambuf_iterator:ostream_type

類型，提供 `ostream_iterator` 的資料流類型。

```cpp
typedef basicOstream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>備註

這個類型與 `basicOstream`\< **CharType**, **Traits**> 同義

### <a name="example"></a>範例

如需如何宣告及使用 `ostream_type` 的範例，請參閱 [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)。

## <a name="ostreambuf_iteratorstreambuf_type"></a><a name="streambuf_type"></a>ostreambuf_iterator::streambuf_type

類型，提供 `ostreambuf_iterator` 的資料流類型。

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>備註

這個類型是`basic_streambuf`\<**CharType**的同義詞,**特徵**>,I/O 緩衝區的流`streambuf`類,當專用於 字元類型**char**時,該類將成為 。

### <a name="example"></a>範例

如需如何宣告及使用 `streambuf_type` 的範例，請參閱 [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)。

## <a name="ostreambuf_iteratortraits_type"></a><a name="traits_type"></a>ostreambuf_iterator:traits_type

類型，提供 `ostream_iterator` 的字元特性類型。

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>備註

此類型是樣板參數 `Traits` 的同義字。

### <a name="example"></a>範例

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
/* Output:
The characters written to the output stream
by charOutBuf are: OUT.
*/
```

## <a name="see-also"></a>另請參閱

[\<反覆運算器>](../standard-library/iterator.md)\
[C++標準庫中的線程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++標準函式庫參考](../standard-library/cpp-standard-library-reference.md)
