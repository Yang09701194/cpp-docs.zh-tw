---
title: 輸出檔資料流成員函式
ms.date: 11/04/2016
helpviewer_keywords:
- output streams [C++], member functions
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
ms.openlocfilehash: 8c23008d0c46a532f11e89442328ed25cc203077
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453059"
---
# <a name="output-file-stream-member-functions"></a>輸出檔資料流成員函式

輸出資料流的成員函式有三種類型：相當於操作工具的類型、會執行未格式化寫入作業的類型，以及其他會修改資料流狀態，且沒有對等的操作工具或插入運算子的類型。 對於循序的格式化輸出，您可能僅會使用插入運算子和操作工具。 對於隨機存取二進位磁碟輸出，您會使用其他的成員函式 (無論搭配插入運算子與否)。

## <a name="the-open-function-for-output-streams"></a>輸出資料流的 open 函式

若要使用輸出檔案資料流程 ([ofstream](../standard-library/basic-ofstream-class.md)), 您必須在函式或`open`函式中將該資料流程與特定的磁片檔案產生關聯。 如果您使用`open`函式, 則可以重複使用與一系列檔案相同的資料流程物件。 不論使用哪一種，描述檔案的引數都一樣。

當您開啟與輸出資料流程相關聯的檔案時, 通常會指定`open_mode`旗標。 您可以使用位元 OR ( &#124; ) 運算子，來合併這些在 `ios` 類別中定義為列舉程式的旗標。 如需列舉程式的清單，請參閱 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)。

有三種常見的輸出資料流情況會牽涉到模式選項：

- 建立檔案。 如果檔案已經存在，將會刪除舊版本檔案。

   ```cpp
   ostream ofile("FILENAME");
   // Default is ios::out

   ofstream ofile("FILENAME", ios::out);
   // Equivalent to above
   ```

- 將記錄附加到現有檔案，或在檔案不存在的情況下建立檔案。

   ```cpp
   ofstream ofile("FILENAME", ios::app);
   ```

- 在相同的資料流上開啟兩個檔案，一次開啟一個。

   ```cpp
   ofstream ofile();
   ofile.open("FILE1", ios::in);
   // Do some output
   ofile.close();    // FILE1 closed
   ofile.open("FILE2", ios::in);
   // Do some more output
   ofile.close();    // FILE2 closed
   // When ofile goes out of scope it is destroyed.
   ```

## <a name="the-put"></a>Put

**put** 函式會將一個字元寫入輸出資料流。 下列兩個陳述式的預設值都相同，但第二個會受到資料流的格式引數影響：

```cpp
cout.put('A');

// Exactly one character written
cout <<'A'; // Format arguments 'width' and 'fill' apply
```

## <a name="the-write"></a>寫入

`write`函式會將記憶體區塊寫入輸出檔案資料流程。 長度引數會指定要寫入的位元組數目。 這個範例會建立輸出檔案資料流，並將 `Date` 結構的二進位值寫入它：

```cpp
// write_function.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;

struct Date
{
   int mo, da, yr;
};

int main( )
{
   Date dt = { 6, 10, 92 };
   ofstream tfile( "date.dat" , ios::binary );
   tfile.write( (char *) &dt, sizeof dt );
}
```

`write`函數在到達 null 字元時不會停止, 因此會寫入完整的類別結構。 函式會採用兩個引數: **char**指標和要寫入的字元計數。 請注意, 在結構物件的位址前面必須轉換成**char** <strong>\*</strong> 。

## <a name="the-seekp-and-tellp-functions"></a>seekp 和 tellp 函式

輸出檔案資料流會保留內部指標，該指標指向接下來要寫入資料的位置。 `seekp` 成員函式會設定此指標，並提供隨機存取磁碟檔案輸出。 `tellp` 成員函式會傳回檔案位置。 如需使用對應至 `seekp` 和 `tellp` 的輸入資料流範例，請參閱 [seekg 和 tellg 函式](../standard-library/input-stream-member-functions.md)。

## <a name="the-close-function-for-output-streams"></a>輸出資料流的 close 函式

`close`成員函式會關閉與輸出檔案資料流程相關聯的磁片檔案。 若要完成所有的磁碟輸出，必須先關閉檔案。 如有需要, `ofstream`此析構函式會為您關閉檔案, 但如果`close`您需要為相同的資料流程物件開啟另一個檔案, 則可以使用函數。

只有當函式或`open`成員函式開啟檔案時, 輸出資料流程的析構函數才會自動關閉資料流程的檔案。 如果您將已開啟檔案的檔案描述元傳遞給此函式, 或`attach`使用成員函式, 則必須明確地關閉檔案。

## <a name="vclrferrorprocessingfunctionsanchor10"></a> 錯誤處理函式

寫入資料流時，請使用下列成員函式來測試是否發生錯誤：

|功能|傳回值|
|--------------|------------------|
|[bad](basic-ios-class.md#bad)|如果有無法復原的錯誤，則傳回 **true**。|
|[fail](basic-ios-class.md#fail)|如果有無法復原的錯誤，或是「預期」的狀況 (例如轉換錯誤，或是找不到檔案)，則傳回 **true**。 `clear`使用零引數呼叫之後, 通常會繼續處理。|
|[good](basic-ios-class.md#good)|如果沒有任何錯誤狀況 (無論是否可復原) 且未設定檔案結尾旗標，則會傳回 **true**。|
|[eof](basic-ios-class.md#eof)|針對檔案結尾條件傳回 **true**。|
|[clear](basic-ios-class.md#clear)|設定內部錯誤狀態。 如果使用預設引數呼叫，它會清除所有錯誤位元。|
|[rdstate](basic-ios-class.md#rdstate|傳回目前的錯誤狀態。|

**!** 會多載運算子, 以執行與`fail`函數相同的函式。 因此運算式︰

```cpp
if(!cout)...
```

等於：

```cpp
if(cout.fail())...
```

**void\*()** 運算子會多載成為相反的 **!** 運算子；因此運算式：

```cpp
if(cout)...
```

等於：

```cpp
if(!cout.fail())...
```

**Void\*()** 運算子不等於, `good`因為它不會測試檔案尾。

## <a name="see-also"></a>另請參閱

[輸出資料流](../standard-library/output-streams.md)
