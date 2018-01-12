---
title: "time、_time32、_time64 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- time
- _time64
- _time32
apilocation:
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
apitype: DLLExport
f1_keywords:
- time
- _time64
- time/time
- time/_time32
- time/_time64
- _time32
dev_langs: C++
helpviewer_keywords:
- time32 function
- _time32 function
- _time64 function
- time functions
- system time
- time64 function
ms.assetid: 280e00f2-2b93-4ece-94cd-e048484c6cc7
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f0e4cd78c6e4da47b7999e6a9dd6c95be93f557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="time-time32-time64"></a>time、_time32、_time64
取得系統時間。  
  
## <a name="syntax"></a>語法  
  
```  
time_t time(  
   time_t *timer   
);  
__time32_t _time32(  
   __time32_t *timer   
);  
__time64_t _time64(  
   __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>參數  
 `timer`  
 時間儲存位置的指標。  
  
## <a name="return-value"></a>傳回值  
 以秒為單位傳回自 1970 年 1 月 1 日午夜所經過的時間，或是如果發生錯誤則傳回 -1。  
  
## <a name="remarks"></a>備註  
 `time` 函式會傳回根據系統時鐘自國際標準時間 (UTC) 1970 年 1 月 1 日午夜 (00:00:00) 起所經過的秒數。 傳回的值會儲存在 `timer`所指定的位置。 此參數可能是 `NULL`，而在此情況下不會儲存傳回的值。  
  
 `time` 是 `_time64` 的包裝函式，而按照預設， `time_t` 相當於 `__time64_t`。 如果您要強制編譯器將 `time_t` 解譯為舊的 32 位元 `time_t`，您可以定義 `_USE_32BIT_TIME_T`。 建議您不要這樣做，原因是您的應用程式可能會在 2038 年 1 月 18 日後失敗；不允許在 64 位元平台上使用此巨集。  
  
## <a name="requirements"></a>需求  
  
|常式傳回的值|必要的標頭|  
|-------------|---------------------|  
|`time`, `_time32`, `_time64`|C: \<time.h>，C++： \<ctime> 或 \<time.h>|  
  
 如需其他相容性資訊，請參閱＜簡介＞中的 [相容性](../../c-runtime-library/compatibility.md) 。  
  
## <a name="example"></a>範例  
  
```C  
// crt_times.c  
// compile with: /W3  
// This program demonstrates these time and date functions:  
//      time         _ftime    ctime_s     asctime_s  
//      _localtime64_s    _gmtime64_s    mktime    _tzset  
//      _strtime_s     _strdate_s  strftime  
//  
// Also the global variable:  
//      _tzname  
//  
// Turn off deprecated unsafe CRT function warnings  
#define _CRT_SECURE_NO_WARNINGS 1  
  
#include <time.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <sys/types.h>  
#include <sys/timeb.h>  
#include <string.h>  
  
int main()  
{  
    char tmpbuf[128], timebuf[26], ampm[] = "AM";  
    time_t ltime;  
    struct _timeb tstruct;  
    struct tm today, gmt, xmas = { 0, 0, 12, 25, 11, 93 };  
    errno_t err;  
  
    // Set time zone from TZ environment variable. If TZ is not set,  
    // the operating system is queried to obtain the default value   
    // for the variable.   
    //  
    _tzset();  
  
    // Display operating system-style date and time.   
    _strtime_s( tmpbuf, 128 );  
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );  
    _strdate_s( tmpbuf, 128 );  
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );  
  
    // Get UNIX-style time and display as number and string.   
    time( &ltime );  
    printf( "Time in seconds since UTC 1/1/70:\t%lld\n", (long long)ltime );  
    err = ctime_s(timebuf, 26, &ltime);  
    if (err)  
    {  
       printf("ctime_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "UNIX time and date:\t\t\t%s", timebuf );  
  
    // Display UTC.   
    err = _gmtime64_s( &gmt, &ltime );  
    if (err)  
    {  
       printf("_gmtime64_s failed due to an invalid argument.");  
    }  
    err = asctime_s(timebuf, 26, &gmt);  
    if (err)  
    {  
       printf("asctime_s failed due to an invalid argument.");  
       exit(1);  
    }  
    printf( "Coordinated universal time:\t\t%s", timebuf );  
  
    // Convert to time structure and adjust for PM if necessary.   
    err = _localtime64_s( &today, &ltime );  
    if (err)  
    {  
       printf("_localtime64_s failed due to an invalid argument.");  
       exit(1);  
    }  
    if( today.tm_hour >= 12 )  
    {  
   strcpy_s( ampm, sizeof(ampm), "PM" );  
   today.tm_hour -= 12;  
    }  
    if( today.tm_hour == 0 )  // Adjust if midnight hour.  
   today.tm_hour = 12;  
  
    // Convert today into an ASCII string   
    err = asctime_s(timebuf, 26, &today);  
    if (err)  
    {  
       printf("asctime_s failed due to an invalid argument.");  
       exit(1);  
    }  
  
    // Note how pointer addition is used to skip the first 11   
    // characters and printf is used to trim off terminating   
    // characters.  
    //  
    printf( "12-hour time:\t\t\t\t%.8s %s\n",  
       timebuf + 11, ampm );  
  
    // Print additional time information.   
    _ftime( &tstruct ); // C4996  
    // Note: _ftime is deprecated; consider using _ftime_s instead  
    printf( "Plus milliseconds:\t\t\t%u\n", tstruct.millitm );  
    printf( "Zone difference in hours from UTC:\t%u\n",   
             tstruct.timezone/60 );  
    printf( "Time zone name:\t\t\t\t%s\n", _tzname[0] ); //C4996  
    // Note: _tzname is deprecated; consider using _get_tzname  
    printf( "Daylight savings:\t\t\t%s\n",   
             tstruct.dstflag ? "YES" : "NO" );  
  
    // Make time for noon on Christmas, 1993.   
    if( mktime( &xmas ) != (time_t)-1 )  
    {  
       err = asctime_s(timebuf, 26, &xmas);  
       if (err)  
       {  
          printf("asctime_s failed due to an invalid argument.");  
          exit(1);  
       }  
       printf( "Christmas\t\t\t\t%s\n", timebuf );  
    }  
  
    // Use time structure to build a customized time string.   
    err = _localtime64_s( &today, &ltime );  
    if (err)  
    {  
        printf(" _localtime64_s failed due to invalid arguments.");  
        exit(1);  
    }  
  
    // Use strftime to build a customized time string.   
    strftime( tmpbuf, 128,  
         "Today is %A, day %d of %B in the year %Y.\n", &today );  
    printf( tmpbuf );  
}  
```  
  
```Output  
OS time:            13:51:23  
OS date:            04/25/03  
Time in seconds since UTC 1/1/70:   1051303883  
UNIX time and date:         Fri Apr 25 13:51:23 2003  
Coordinated universal time:      Fri Apr 25 20:51:23 2003  
12-hour time:            01:51:23 PM  
Plus milliseconds:         552  
Zone difference in hours from UTC:   8  
Time zone name:            Pacific Standard Time  
Daylight savings:         YES  
Christmas            Sat Dec 25 12:00:00 1993  
  
Today is Friday, day 25 of April in the year 2003.  
```  
  
## <a name="see-also"></a>請參閱  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)