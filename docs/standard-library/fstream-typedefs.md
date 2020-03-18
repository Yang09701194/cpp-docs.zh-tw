---
title: '&lt;fstream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
ms.openlocfilehash: 3f4104b28f5becfdbf62ede16faa81e855fcac8c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421776"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a>  filebuf

類型 `basic_filebuf` 在**char**樣板參數上特製化。

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_filebuf](../standard-library/basic-filebuf-class.md)的同義字，專門用於具有預設字元特性之**char**類型的元素。

## <a name="fstream"></a>  fstream

類型 `basic_fstream` 在**char**樣板參數上特製化。

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_fstream](../standard-library/basic-fstream-class.md)的同義字，專門用於具有預設字元特性之**char**類型的元素。

## <a name="ifstream"></a>  ifstream

定義用來從檔案連續讀取單一位元組字元的資料流。 `ifstream` 是一種 typedef，專門針對**char**`basic_ifstream` 的類別樣板。

另外還有 `wifstream`，其專門用來 `basic_ifstream` 讀取**wchar_t**全半形字元的 typedef。 如需詳細資訊，請參閱 [wifstream](../standard-library/fstream-typedefs.md#wifstream)。

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_ifstream](../standard-library/basic-ifstream-class.md)的同義字，專門用於具有預設字元特性之 char 類型的元素。 例如，

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a>  ofstream

類型 `basic_ofstream` 在**char**樣板參數上特製化。

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_ofstream](../standard-library/basic-ofstream-class.md)的同義字，專門用於具有預設字元特性之**char**類型的元素。

## <a name="wfstream"></a>  wfstream

類型 `basic_fstream` 在**wchar_t**樣板參數上特製化。

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_fstream](../standard-library/basic-fstream-class.md)的同義字，專門用於具有預設字元特性**wchar_t**類型的元素。

## <a name="wifstream"></a>  wifstream

類型 `basic_ifstream` 在**wchar_t**樣板參數上特製化。

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_ifstream](../standard-library/basic-ifstream-class.md)的同義字，專門用於具有預設字元特性**wchar_t**類型的元素。

## <a name="wofstream"></a>  wofstream

類型 `basic_ofstream` 在**wchar_t**樣板參數上特製化。

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_ofstream](../standard-library/basic-ofstream-class.md)的同義字，專門用於具有預設字元特性**wchar_t**類型的元素。

## <a name="wfilebuf"></a>  wfilebuf

類型 `basic_filebuf` 在**wchar_t**樣板參數上特製化。

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>備註

此類型是類別樣板[basic_filebuf](../standard-library/basic-filebuf-class.md)的同義字，專門用於具有預設字元特性**wchar_t**類型的元素。

## <a name="see-also"></a>另請參閱

[\<fstream>](../standard-library/fstream.md)
