---
title: collate 類別
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate
- locale/std::collate::char_type
- locale/std::collate::string_type
- locale/std::collate::compare
- locale/std::collate::do_compare
- locale/std::collate::do_hash
- locale/std::collate::do_transform
- locale/std::collate::hash
- locale/std::collate::transform
helpviewer_keywords:
- std::collate [C++]
- std::collate [C++], char_type
- std::collate [C++], string_type
- std::collate [C++], compare
- std::collate [C++], do_compare
- std::collate [C++], do_hash
- std::collate [C++], do_transform
- std::collate [C++], hash
- std::collate [C++], transform
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
ms.openlocfilehash: f05c2e9482f8a0bada3868fdc946d4d26a0e0e1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371928"
---
# <a name="collate-class"></a>collate 類別

一個類範本,用於描述可用作區域設置面的物件,用於控制字串中字元的順序和分組、字串之間的比較和字串的哈希。

## <a name="syntax"></a>語法

```cpp
template <class CharType>
class collate : public locale::facet;
```

### <a name="parameters"></a>參數

*字元類型*\
用於程式內部字元編碼的類型。

## <a name="remarks"></a>備註

如同所有地區設定 facet，靜態物件識別碼有初始儲存值零。 第一次嘗試存取其預存值時，會在 `id` 中儲存唯一的正值。 在某些語言中，字元視為單一字元群組及處理，而且在其他語言中，個別字元視為兩個字元。 collate 類別提供的定序服務提供排序這些案例的方式。

### <a name="constructors"></a>建構函式

|建構函式|描述|
|-|-|
|[整理](#collate)|做為地區設定 facet 處理字串排序慣例之 `collate` 類別物件的建構函式。|

### <a name="typedefs"></a>Typedefs

|類型名稱|描述|
|-|-|
|[char_type](#char_type)|類型，描述 `CharType` 類型之字元。|
|[string_type](#string_type)|類型，描述包含 `basic_string` 類型字元的 `CharType` 類型字串。|

### <a name="member-functions"></a>成員函數

|成員函數|描述|
|-|-|
|[比較](#compare)|根據其 facet 特定規則，比較兩個字元序列相等或不等。|
|[do_compare](#do_compare)|虛擬函式，呼叫以根據其 facet 特定規則，比較兩個字元序列相等或不等。|
|[do_hash](#do_hash)|虛擬函式，呼叫以根據其 facet 特定規則，決定序列的雜湊值。|
|[do_transform](#do_transform)|虛擬函式，呼叫以將地區設定的字元序列轉換為字串，可用來與從相同地區設定轉換的其他字元序列進行語彙比較。|
|[散 列](#hash)|根據其 facet 特定規則，決定序列的雜湊值。|
|[變換](#transform)|將地區設定的字元序列轉換為字串，可用來與從相同地區設定轉換的其他字元序列進行語彙比較。|

## <a name="requirements"></a>需求

**標頭︰** \<locale>

**命名空間：** std

## <a name="collatechar_type"></a><a name="char_type"></a>整理::char_type

類型，描述 `CharType` 類型之字元。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>備註

此類型是樣板參數 `CharType` 的同義字。

## <a name="collatecollate"></a><a name="collate"></a>整理::整理

collate 類別物件的建構函式，可作為地區設定 Facet 以處理字串排序慣例。

```cpp
public:
    explicit collate(
    size_t _Refs = 0);

protected:
    collate(
const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>參數

*_Refs*\
整數值，用來指定物件的記憶體管理類型。

*_Locname*\
地區設定的名稱。

### <a name="remarks"></a>備註

*_Refs*參數的可能值及其顯著性為:

- 0：物件的存留期由包含該物件的地區設定來管理。

- 1：物件的存留期必須以手動方式管理。

- \>1: 未定義這些值。

建構函式用區域設定初始化其基本物件 **::**[分面](../standard-library/locale-class.md#facet_class)(`_Refs`。

## <a name="collatecompare"></a><a name="compare"></a>整理::比較

根據其 facet 特定規則，比較兩個字元序列相等或不等。

```cpp
int compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>參數

*第一1*\
要比較之第一個序列中第一個元素的指標。

*最後1*\
要比較之第一個序列中最後一個元素的指標。

*第一2*\
要比較之第二個序列中第一個元素的指標。

*最後2*\
要比較之第二個序列中最後一個元素的指標。

### <a name="return-value"></a>傳回值

成員函式會傳回：

- –1，表示第一個序列比第二個序列小。

- +1，表示第二個序列比第一個序列小。

- 0，表示序列相等。

### <a name="remarks"></a>備註

第一個序列比較小，表示第一個序列具有序列中最早出現之不相等配對中較小的元素，或者，表示不相等配對存在，但第一個序列較短。

成員函數傳[do_compare](#do_compare)`first1`回 do_compare `last1` `first2` `last2`(、 、 )

### <a name="example"></a>範例

```cpp
// collate_compare.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare ( s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << result2 << endl;
}
```

## <a name="collatedo_compare"></a><a name="do_compare"></a>整理::do_比較

虛擬函式，呼叫以根據其 facet 特定規則，比較兩個字元序列相等或不等。

```cpp
virtual int do_compare(const CharType* first1,
    const CharType* last1,
    const CharType* first2,
    const CharType* last2) const;
```

### <a name="parameters"></a>參數

*第一1*\
要比較之第一個序列中第一個元素的指標。

*最後1*\
要比較之第一個序列中最後一個元素的指標。

*第一2*\
要比較之第二個序列中第一個元素的指標。

*最後2*\
要比較之第二個序列中最後一個元素的指標。

### <a name="return-value"></a>傳回值

成員函式會傳回：

- –1，表示第一個序列比第二個序列小。

- +1，表示第二個序列比第一個序列小。

- 0，表示序列相等。

### <a name="remarks"></a>備註

受保護的虛擬成員函數將 * 前 11,Last1)] 處的序列與 *# first2, last2*的序列進行比較。 它通過在類型`CharType`對應`operator<`元素的對之間應用來比較值。 第一個序列比較小，表示第一個序列具有序列中最早出現之不相等配對中較小的元素，或表示不相等配對存在，但第一個序列較短。

### <a name="example"></a>範例

請參閱 [collate::compare](#compare) 的範例，其會呼叫 `do_compare`。

## <a name="collatedo_hash"></a><a name="do_hash"></a>整理::d

虛擬函式，呼叫以根據其 facet 特定規則，決定序列的雜湊值。

```cpp
virtual long do_hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>參數

*第一*\
要決定其序列值之第一個字元的指標。

*最後*\
要決定其序列值之最後一個字元的指標。

### <a name="return-value"></a>傳回值

序列之 **long** 類型的雜湊值。

### <a name="remarks"></a>備註

雜湊值非常適合在清單陣列之間虛擬隨機散發序列。

### <a name="example"></a>範例

請參閱 [hash](#hash) 的範例，其會呼叫 `do_hash`。

## <a name="collatedo_transform"></a><a name="do_transform"></a>整理::do_變換

虛擬函式，呼叫以將地區設定的字元序列轉換為字串，可用來與從相同地區設定轉換的其他字元序列進行語彙比較。

```cpp
virtual string_type do_transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>參數

*第一*\
要轉換之序列中第一個字元的指標。

*最後*\
要轉換之序列中最後一個字元的指標。

### <a name="return-value"></a>傳回值

字串，其為已轉換的字元序列。

### <a name="remarks"></a>備註

受保護的虛擬成員函數傳回類別[string_type的物件,](#string_type)其受控序列是序列的複`first``last`本 * 。 如果衍生自 collate\< **CharType**> 的類別會覆寫 [do_compare](#do_compare)，該類別也會覆寫 `do_transform` 以彼此相符。 相較於傳遞要在衍生類別中比較的未轉換字串，若將兩個已轉換的字串傳遞至 `collate::compare`，應該可以產生相同結果。

### <a name="example"></a>範例

請參閱 [transform](#transform) 的範例，其會呼叫 `do_transform`。

## <a name="collatehash"></a><a name="hash"></a>整理::哈希

根據其 facet 特定規則，決定序列的雜湊值。

```cpp
long hash(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>參數

*第一*\
要決定其序列值之第一個字元的指標。

*最後*\
要決定其序列值之最後一個字元的指標。

### <a name="return-value"></a>傳回值

序列之 **long** 類型的雜湊值。

### <a name="remarks"></a>備註

成員函數返回[do_hash](#do_hash) `first` `last` (。

雜湊值非常適合在清單陣列之間虛擬隨機散發序列。

### <a name="example"></a>範例

```cpp
// collate_hash.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("\x00dfzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet
   _TCHAR * s2 = _T("zzz abc."); // \x00df is the German sharp-s (looks like beta), it comes before z in the alphabet

   long r1 = use_facet< collate<_TCHAR> > ( loc ).
      hash (s1, &s1[_tcslen( s1 )-1 ]);
   long r2 =  use_facet< collate<_TCHAR> > ( loc ).
      hash (s2, &s2[_tcslen( s2 )-1 ] );
   cout << r1 << " " << r2 << endl;
}
```

```Output
541187293 551279837
```

## <a name="collatestring_type"></a><a name="string_type"></a>整理::string_type

類型，描述包含 `basic_string` 類型字元的 `CharType` 類型字串。

```cpp
typedef basic_string<CharType> string_type;
```

### <a name="remarks"></a>備註

類型描述類範本的專門化[basic_string](../standard-library/basic-string-class.md)其物件可以存儲源序列的副本。

### <a name="example"></a>範例

如需如何宣告和使用 `string_type` 的範例，請參閱 [transform](#transform)。

## <a name="collatetransform"></a><a name="transform"></a>整理::轉換

將地區設定的字元序列轉換為字串，可用來與從相同地區設定轉換的其他字元序列進行語彙比較。

```cpp
string_type transform(const CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>參數

*第一*\
要轉換之序列中第一個字元的指標。

*最後*\
要轉換之序列中最後一個字元的指標。

### <a name="return-value"></a>傳回值

字串，其包含已轉換的字元序列。

### <a name="remarks"></a>備註

成員函數返回[do_transform](#do_transform)`first` `last` (。

### <a name="example"></a>範例

```cpp
// collate_transform.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   _TCHAR* s1 = _T("\x00dfzz abc.");
   // \x00df is the German sharp-s (looks like beta),
   // it comes before z in the alphabet
   _TCHAR* s2 = _T("zzz abc.");

   collate<_TCHAR>::string_type r1;   // OK for typedef
   r1 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s1, &s1[_tcslen( s1 )-1 ]);

   cout << r1 << endl;

   basic_string<_TCHAR> r2 = use_facet< collate<_TCHAR> > ( loc ).
      transform (s2, &s2[_tcslen( s2 )-1 ]);

   cout << r2 << endl;

   int result1 = use_facet<collate<_TCHAR> > ( loc ).compare
      (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );

   cout << _tcscmp(r1.c_str( ),r2.c_str( )) << result1
      << _tcscmp(s1,s2) <<endl;
}
```

```Output

-1-11
```

## <a name="see-also"></a>另請參閱

[\<區域設定>](../standard-library/locale.md)\
[C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
