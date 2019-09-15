---
title: _ftime_s、_ftime32_s、_ftime64_s
ms.date: 11/04/2016
api_name:
- _ftime_s
- _ftime64_s
- _ftime32_s
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
- api-ms-win-crt-time-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftime_s
- _ftime64_s
- ftime_s
- _ftime32_s
- ftime32_s
- ftime64_s
helpviewer_keywords:
- ftime32_s function
- ftime_s function
- _ftime64_s function
- current time
- ftime64_s function
- time, getting current
- _ftime_s function
- _ftime32_s function
ms.assetid: d03080d9-a520-45be-aa65-504bdb197e8b
ms.openlocfilehash: b45a22afc824a33e81170f954e6f99088b629f83
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956317"
---
# <a name="_ftime_s-_ftime32_s-_ftime64_s"></a>_ftime_s、_ftime32_s、_ftime64_s

取得目前時間。 這些是具有 [CRT 中的安全性功能](../../c-runtime-library/security-features-in-the-crt.md)中所述之安全性增強功能的 [_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md) 版本。

## <a name="syntax"></a>語法

```C
errno_t _ftime_s( struct _timeb *timeptr );
errno_t _ftime32_s( struct __timeb32 *timeptr );
errno_t _ftime64_s( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>參數

*timeptr*<br/>
**_Timeb**、 **__timeb32**或 **__timeb64**結構的指標。

## <a name="return-value"></a>傳回值

如果成功，則為零，如果失敗，則為錯誤碼。 如果*timeptr*為**Null**，則傳回值為**EINVAL**。

## <a name="remarks"></a>備註

**_Ftime_s**函式會取得目前的當地時間，並將它儲存在*timeptr*所指向的結構中。 **_Timeb**、 **__timeb32**和 **__timeb64**結構定義于于 sys\timeb.h 中。 它們包含下表中所列出的四個欄位。

|欄位|描述|
|-|-|
|**dstflag**|若日光節約時間目前於本地時區已生效，則為非零。 (如需如何判斷日光節約時間的說明，請參閱 [_tzset](tzset.md)。)|
|**millitm**|秒數的分數，以毫秒為單位。|
|**time**|自國際標準時間 (UTC) 1970 年 1 月 1 日午夜 (00:00:00) 以來的時間，以秒為單位。|
|**timezone**|UTC 和當地時間之間的時差，向西推進，以分鐘為單位。 [**時區**] 的值是從全域變數 **_timezone**的值設定的（請參閱 **_tzset**）。|

使用 **__timeb64**結構的 **_ftime64_s**函式可讓檔案建立日期以23:59:59 年12月31日3000，UTC 表示。雖然 **_ftime32_s**只代表日期到23:59:59 年1月 18 2038 日，UTC。 1970 年 1 月 1 日午夜是所有這些函式的日期範圍下限。

**_Ftime_s**函數相當於 **_ftime64_s**，而 **_timeb**包含64位時間，除非已定義 **_USE_32BIT_TIME_T** ，在此情況下，舊的行為會生效; **_ftime_s**使用32位時間，而 **_timeb**包含32位時間。

**_ftime_s**會驗證其參數。 如果將 null 指標傳遞為*timeptr*，則函式會叫用不正確參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果允許繼續執行，函式會將**errno**設定為**EINVAL**。

## <a name="requirements"></a>需求

|函數|必要的標頭|
|--------------|---------------------|
|**_ftime_s**|\<sys/types.h> 和 \<sys/timeb.h>|
|**_ftime32_s**|\<sys/types.h> 和 \<sys/timeb.h>|
|**_ftime64_s**|\<sys/types.h> 和 \<sys/timeb.h>|

如需相容性的詳細資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>程式庫

所有版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。

## <a name="example"></a>範例

```C
// crt_ftime64_s.c
// This program uses _ftime64_s to obtain the current
// time and then stores this time in timebuffer.

#include <stdio.h>
#include <sys/timeb.h>
#include <time.h>

int main( void )
{
   struct _timeb timebuffer;
   char timeline[26];
   errno_t err;
   time_t time1;
   unsigned short millitm1;
   short timezone1;
   short dstflag1;

   _ftime64_s( &timebuffer );

    time1 = timebuffer.time;
    millitm1 = timebuffer.millitm;
    timezone1 = timebuffer.timezone;
    dstflag1 = timebuffer.dstflag;

   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",
   time1);
   printf( "Milliseconds: %d\n", millitm1);
   printf( "Minutes between UTC and local time: %d\n", timezone1);
   printf( "Daylight savings time flag (1 means Daylight time is in "
           "effect): %d\n", dstflag1);

   err = ctime_s( timeline, 26, & ( timebuffer.time ) );
   if (err)
   {
       printf("Invalid argument to ctime_s. ");
   }
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,
           &timeline[20] );
}
```

```Output
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>另請參閱

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
