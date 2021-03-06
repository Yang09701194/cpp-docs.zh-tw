---
title: _heapchk
ms.date: 4/2/2020
api_name:
- _heapchk
- _o__heapchk
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _heapchk
- heapchk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
ms.openlocfilehash: 2ddbdaec5861d48cc23a7cbcd28332e8c06ebbfe
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916205"
---
# <a name="_heapchk"></a>_heapchk

在堆積上執行一致性檢查。

## <a name="syntax"></a>語法

```C
int _heapchk( void );
```

## <a name="return-value"></a>傳回值

**_heapchk**會傳回在 Malloc. h 中定義的下列其中一個整數資訊清單常數。

|傳回值|條件|
|-|-|
| **_HEAPBADBEGIN** | 初始標頭資訊不正確或找不到。 |
| **_HEAPBADNODE** | 找到不正確的節點或堆積損壞。 |
| **_HEAPBADPTR** | 無效的堆積指標。 |
| **_HEAPEMPTY** | 堆積尚未初始化。 |
| **_HEAPOK** | 堆積看似一致。 |

此外，如果發生錯誤， **_heapchk**會將**Errno**設定為**ENOSYS**。

## <a name="remarks"></a>備註

**_Heapchk**函數藉由檢查堆積的最小一致性，協助您進行堆積相關的問題。 如果作業系統不支援 **_heapchk**（例如 Windows 98），此函式會傳回 **_HEAPOK** ，並將**errno**設定為**ENOSYS**。

根據預設，此函式的全域狀態範圍設定為應用程式。 若要變更此項，請參閱[CRT 中的全域狀態](../global-state.md)。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|選擇性標頭|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc.h>|\<errno.h>|

如需詳細的相容性資訊，請參閱 [Compatibility](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>範例

```C
// crt_heapchk.c
// This program checks the heap for
// consistency and prints an appropriate message.

#include <malloc.h>
#include <stdio.h>

int main( void )
{
   int  heapstatus;
   char *buffer;

   // Allocate and deallocate some memory
   if( (buffer = (char *)malloc( 100 )) != NULL )
      free( buffer );

   // Check heap status
   heapstatus = _heapchk();
   switch( heapstatus )
   {
   case _HEAPOK:
      printf(" OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf(" OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>另請參閱

[記憶體配置](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
