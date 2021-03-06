---
title: sprintf_s、_sprintf_s_l、swprintf_s、_swprintf_s_l
ms.date: 11/04/2016
api_name:
- _swprintf_s_l
- _sprintf_s_l
- swprintf_s
- sprintf_s
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- swprintf_s
- sprintf_s
- stdio/sprintf_s
- stdio/swprintf_s
- stdio/_sprintf_s_l
- stdio/_swprintf_s_l
- _sprintf_s_l
- _swprintf_s_l
helpviewer_keywords:
- stprintf_s function
- stprintf_s_l function
- swprintf_s_l function
- sprintf_s function
- swprintf_s function
- _swprintf_s_l function
- sprintf_s_l function
- _stprintf_s_l function
- _stprintf_s function
- _sprintf_s_l function
- formatted text [C++]
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
ms.openlocfilehash: 34b3ddce68563479b26abff34e8fa31f6298558a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958014"
---
# <a name="sprintf_s-_sprintf_s_l-swprintf_s-_swprintf_s_l"></a>sprintf_s、_sprintf_s_l、swprintf_s、_swprintf_s_l

將格式化資料寫入字串。 這些是具有 [CRT 中的安全性功能](../../c-runtime-library/security-features-in-the-crt.md)中所述之安全性增強功能的 [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) 版本。

## <a name="syntax"></a>語法

```C
int sprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   ...
);
int _sprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   locale_t locale,
   ...
);
int swprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   ...
);
int _swprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   locale_t locale,
   ...
);
template <size_t size>
int sprintf_s(
   char (&buffer)[size],
   const char *format,
   ...
); // C++ only
template <size_t size>
int swprintf_s(
   wchar_t (&buffer)[size],
   const wchar_t *format,
   ...
); // C++ only
```

### <a name="parameters"></a>參數

*buffer*<br/>
輸出的儲存位置

*sizeOfBuffer*<br/>
要儲存的最大字元數。

*格式*<br/>
格式控制字串

*...*<br/>
要進行格式化的選擇性引數

*locale*<br/>
要使用的地區設定。

如需詳細資訊，請參閱 [格式規格](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)。

## <a name="return-value"></a>傳回值

寫入的字元數，如果發生錯誤，則為-1。 如果*buffer*或*format*是 null 指標，則**sprintf_s**和**swprintf_s**會傳回-1，並將**errno**設定為**EINVAL**。

**sprintf_s**會傳回儲存在*緩衝區*中的位元組數目，而不會計算終止的 null 字元。 **swprintf_s**會傳回儲存在*緩衝區*中的寬字元數，而不會計算終止的 null 寬字元。

## <a name="remarks"></a>備註

**Sprintf_s**函式會格式化並將一連串的字元和值儲存在*buffer*中。 每個*引數*（如果有的話）都會根據*格式*的對應格式規格進行轉換和輸出。 此格式包含一般字元，與[printf](printf-printf-l-wprintf-wprintf-l.md)的*format*引數具有相同的形式和功能。 null 字元會附加至最後一個寫入的字元之後。 如果在重疊的字串之間進行複製，則行為是未定義的。

**Sprintf_s**和[sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)之間的主要差異在於**sprintf_s**會檢查格式字串是否有有效的格式設定字元，而[sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)只會檢查格式字串或緩衝區是否為**Null**指標。 若其中一個檢查失敗，就會叫用無效的參數處理常式，如 [Parameter Validation](../../c-runtime-library/parameter-validation.md)所述。 如果允許繼續執行，此函式會傳回-1，並將**errno**設定為**EINVAL**。

**Sprintf_s**和[sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)之間的另一個主要差異在於， **sprintf_s**會採用長度參數來指定輸出緩衝區的大小（以字元為單位）。 如果緩衝區對格式化文字而言太小（包括終止的 null），則會將 null 字元放在*緩衝區*[0]，並叫用不正確參數處理常式，將緩衝區設為空字串。 不同于 **_snprintf**， **sprintf_s**保證緩衝區會以 null 結束，除非緩衝區大小為零。

**swprintf_s**是寬字元版本的**sprintf_s**;**swprintf_s**的指標引數是寬字元字串。 **Swprintf_s**中的編碼錯誤偵測可能與**sprintf_s**中的不同。 這些具有 **_l**尾碼的函式版本都相同，不同之處在于它們會使用傳入的地區設定參數，而不是目前的執行緒地區設定。

在 C++ 中，範本多載簡化了這些函式的使用方式。多載可自動推斷緩衝區長度 (因而不需指定大小引數)，也可將不安全的較舊函式自動取代成較新且安全的對應函式。 如需詳細資訊，請參閱 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)。

有一些**sprintf_s**版本可讓您進一步控制緩衝區太小時所發生的情況。 如需詳細資訊，請參閱 [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)。

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf_s**|**sprintf_s**|**sprintf_s**|**swprintf_s**|
|**_stprintf_s_l**|**_sprintf_s_l**|**_sprintf_s_l**|**_swprintf_s_l**|

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**sprintf_s**、 **_sprintf_s_l**|C：\<stdio.h><br /><br /> C++：\<cstdio> 或 \<stdio.h>|
|**swprintf_s**、 **_swprintf_s_l**|C：\<stdio.h> 或 \<wchar.h><br /><br /> C++：\<cstdio>、\<cwchar>、\<stdio.h> 或 \<wchar.h>|

如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>範例

```C
// crt_sprintf_s.c
// This program uses sprintf_s to format various
// data and place them in the string named buffer.
//

#include <stdio.h>

int main( void )
{
   char  buffer[200], s[] = "computer", c = 'l';
   int   i = 35, j;
   float fp = 1.7320534f;

   // Format and print various data:
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );

   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );
}
```

```Output
Output:
   String:    computer
   Character: l
   Integer:   35
   Real:      1.732053

character count = 79
```

## <a name="example"></a>範例

```C
// crt_swprintf_s.c
// wide character example
// also demonstrates swprintf_s returning error code
#include <stdio.h>

int main( void )
{
   wchar_t buf[100];
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );
   printf( "wrote %d characters\n", len );
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );
   // swprintf_s fails because string contains WEOF (\xffff)
   printf( "wrote %d characters\n", len );
}
```

```Output
wrote 11 characters
wrote -1 characters
```

## <a name="see-also"></a>另請參閱

[資料流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[scanf、_scanf_l、wscanf、_wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf、_sscanf_l、swscanf、_swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf 函式](../../c-runtime-library/vprintf-functions.md)<br/>
