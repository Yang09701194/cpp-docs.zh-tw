---
title: _flushall
ms.date: 4/2/2020
api_name:
- _flushall
- _o__flushall
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
- _flushall
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
ms.openlocfilehash: 1a53eeedd5dfa0f9c01fa5883a9db33e26e3ea17
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911617"
---
# <a name="_flushall"></a>_flushall

清除所有資料流；清除所有緩衝區。

## <a name="syntax"></a>語法

```C
int _flushall( void );
```

## <a name="return-value"></a>傳回值

**_flushall**會傳回開啟的資料流程數目（輸入和輸出）。 不會傳回錯誤。

## <a name="remarks"></a>備註

根據預設， **_flushall**函式會將與開啟的輸出資料流程相關聯之所有緩衝區的內容寫入適當的檔案。 會清除與開啟之輸入資料流相關聯的所有緩衝區中的目前內容 (這些緩衝區通常是由作業系統所維護，以判斷將資料自動寫入至磁碟的最佳時機︰緩衝區已滿時、關閉資料流時，或程式正常結束而未關閉資料流時)。

如果讀取會遵循 **_flushall**的呼叫，則會從輸入檔案將新資料讀取到緩衝區。 在呼叫 **_flushall**之後，所有資料流程都會保持開啟狀態。

執行階段程式庫的認可到磁碟功能可讓您確保將重大資料直接寫入至磁碟，而不是作業系統緩衝區。 若不重寫現有的程式，您可以將程式的物件檔與 Commode.obj 連結，以啟用此功能。在產生的可執行檔中，呼叫 **_flushall**將所有緩衝區的內容寫入磁片。 只有 **_flushall**和[Fflush](fflush.md)會受到 commode.obj 的影響。

如需控制認可到磁碟功能的資訊，請參閱[資料流 I/O](../../c-runtime-library/stream-i-o.md)、[fopen](fopen-wfopen.md) 和 [_fdopen](fdopen-wfdopen.md)。

根據預設，此函式的全域狀態範圍設定為應用程式。 若要變更此項，請參閱[CRT 中的全域狀態](../global-state.md)。

## <a name="requirements"></a>需求

|函式|必要的標頭|
|--------------|---------------------|
|**_flushall**|\<stdio.h>|

如需詳細的相容性資訊，請參閱 [Compatibility](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>範例

```C
// crt_flushall.c
// This program uses _flushall
// to flush all open buffers.

#include <stdio.h>

int main( void )
{
   int numflushed;

   numflushed = _flushall();
   printf( "There were %d streams flushed\n", numflushed );
}
```

```Output
There were 3 streams flushed
```

## <a name="see-also"></a>另請參閱

[資料流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_commit](commit.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[setvbuf](setvbuf.md)<br/>
