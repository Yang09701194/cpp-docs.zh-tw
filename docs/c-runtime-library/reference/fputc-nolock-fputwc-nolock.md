---
title: _fputc_nolock、_fputwc_nolock
ms.date: 4/2/2020
api_name:
- _fputwc_nolock
- _fputc_nolock
- _o__fputc_nolock
- _o__fputwc_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fputc_nolock
- fputwc_nolock
- fputc_nolock
- fputtc_nolock
- _fputwc_nolock
- _fputtc_nolock
helpviewer_keywords:
- streams, writing characters to
- fputwc_nolock function
- fputtc_nolock function
- _fputc_nolock function
- fputc_nolock function
- _fputtc_nolock function
- _fputwc_nolock function
ms.assetid: c63eb3ad-58fa-46d0-9249-9c25f815eab9
ms.openlocfilehash: e25539bf6c6d590a787615e091ec68753cd1c93e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920132"
---
# <a name="_fputc_nolock-_fputwc_nolock"></a>_fputc_nolock、_fputwc_nolock

將字元寫入至資料流，而不需要鎖定執行緒。

## <a name="syntax"></a>語法

```C
int _fputc_nolock(
   int c,
   FILE *stream
);
wint_t _fputwc_nolock(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>參數

*c*<br/>
待寫入字元。

*資料流*<br/>
**FILE** 結構的指標。

## <a name="return-value"></a>傳回值

所有這些函式都會傳回寫入的字元。 如需錯誤資訊，請參閱 [fputc、fputwc](fputc-fputwc.md)。

## <a name="remarks"></a>備註

**_fputc_nolock**和 **_fputwc_nolock**分別與**fputc**和**fputwc**相同，不同之處在于它們不會受到保護，不受其他執行緒的干擾。 因為它們不會造成鎖定其他執行緒的額外負荷，所以可能會比較快。 這些函式只能用在安全執行緒內容 (例如單一執行緒應用程式) 或呼叫範圍已經處理執行緒隔離的地方。

如果資料流是以 ANSI 模式開啟，則這兩個函式的行為相同。 **_fputc_nolock**目前不支援輸出至 UNICODE 資料流程。

根據預設，此函式的全域狀態範圍設定為應用程式。 若要變更此項，請參閱[CRT 中的全域狀態](../global-state.md)。

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|Tchar.h 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fputtc_nolock**|**_fputc_nolock**|**_fputc_nolock**|**_fputwc_nolock**|

## <a name="requirements"></a>需求

|函式|必要的標頭|
|--------------|---------------------|
|**_fputc_nolock**|\<stdio.h>|
|**_fputwc_nolock**|\<stdio.h> 或 \<wchar.h>|

通用 Windows 平臺（UWP）應用程式中不支援主控台。 與主控台相關聯的標準資料流程控制碼（**stdin**、 **stdout**和**stderr**）必須先重新導向，C 執行時間函式才能在 UWP 應用程式中使用它們。 如需詳細的相容性資訊，請參閱 [Compatibility](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>範例

```C
// crt_fputc_nolock.c
// This program uses _fputc_nolock
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of _fputc_nolock!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && _fputc_nolock( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of _fputc_nolock!!
```

## <a name="see-also"></a>另請參閱

[資料流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc、fgetwc](fgetc-fgetwc.md)<br/>
[putc、putwc](putc-putwc.md)<br/>
