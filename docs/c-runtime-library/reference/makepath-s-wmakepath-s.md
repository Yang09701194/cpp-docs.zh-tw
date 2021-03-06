---
title: _makepath_s、_wmakepath_s
ms.date: 4/2/2020
api_name:
- _wmakepath_s
- _makepath_s
- _o__makepath_s
- _o__wmakepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
ms.openlocfilehash: 8eb3cf338d7486d7e7893090a1390e5d2d16a438
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914484"
---
# <a name="_makepath_s-_wmakepath_s"></a>_makepath_s、_wmakepath_s

從元件建立路徑名稱。 這些是 [_makepath、_wmakepath](makepath-wmakepath.md) 的版本，具有 [CRT 中的安全性功能](../../c-runtime-library/security-features-in-the-crt.md)中所述的安全性增強功能。

## <a name="syntax"></a>語法

```C
errno_t _makepath_s(
   char *path,
   size_t sizeInBytes,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
errno_t _wmakepath_s(
   wchar_t *path,
   size_t sizeInWords,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
template <size_t size>
errno_t _makepath_s(
   char (&path)[size],
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
); // C++ only
template <size_t size>
errno_t _wmakepath_s(
   wchar_t (&path)[size],
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
); // C++ only
```

### <a name="parameters"></a>參數

*path*<br/>
完整路徑緩衝區。

*sizeInWords*<br/>
以字組為單位的緩衝區大小。

*sizeInBytes*<br/>
以位元組為單位的緩衝區大小。

*硬碟磁碟機*<br/>
包含對應至所需磁碟機的代號 (A、B 等) 及選擇性後置冒號。 **_makepath_s**在複合路徑中自動插入冒號（如果遺漏的話）。 如果*drive*是**Null**或指向空字串，複合*路徑*字串中就不會出現任何磁碟機號。

*dir*<br/>
包含目錄路徑，但不包含磁碟機指示項或實際檔案名稱。 尾端斜線是選擇性的，而且可以在單一*dir*引數中使用正斜線（\\/）或反斜線（）或兩者。 如果未指定後置斜線 (/ 或\\)，則會自動插入。 如果*dir*是**Null**或指向空字串，複合*路徑*字串中就不會插入任何目錄路徑。

*fname*<br/>
包含基底檔案名稱，但不包含任何副檔名。 如果*fname*為**Null**或指向空字串，複合*路徑*字串中就不會插入任何檔案名。

*分機*<br/>
包含實際副檔名，可包含或不含前置句號 (.)。 如果未出現在*ext*中， **_makepath_s**會自動插入句號。如果*ext*是**Null**或指向空字串，複合*路徑*字串中就不會插入任何副檔名。

## <a name="return-value"></a>傳回值

如果成功，就是零，如果失敗，則為錯誤碼。

### <a name="error-conditions"></a>錯誤狀況

|*path*|*sizeInWords* / *sizeInBytes*|傳回|*路徑*的內容|
|------------|------------------------------------|------------|------------------------|
|**Null**|任意|**EINVAL**|未修改|
|任意|<= 0|**EINVAL**|未修改|

如果發生上述任何一種錯誤狀況，則這些函式會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果允許繼續執行， **errno**會設為**EINVAL** ，而函數會傳回**EINVAL**。 參數*drive*、 *fname*和*ext*允許**Null** 。如需這些參數為 null 指標或空字串時之行為的詳細資訊，請參閱備註一節。

## <a name="remarks"></a>備註

**_Makepath_s**函式會從個別元件建立複合路徑字串，並將結果儲存在*path*中。 *路徑*可能包含磁碟機號、目錄路徑、檔案名和副檔名。 **_wmakepath_s**是寬字元版本的 **_makepath_s**;**_wmakepath_s**的引數是寬字元字串。 相反地， **_wmakepath_s**和 **_makepath_s**的行為相同。

根據預設，此函式的全域狀態範圍設定為應用程式。 若要變更此項，請參閱[CRT 中的全域狀態](../global-state.md)。

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|Tchar.h 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*Path*引數必須指向夠大的空緩衝區，以容納完整的路徑。 複合*路徑*不能大於 stdlib.h> 中定義的 **_MAX_PATH**常數。

如果 path 為**Null**，則會叫用不正確參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 此外， **errno**會設定為**EINVAL**。 所有其他參數都允許**Null**值。

C++ 利用多載樣板簡化了這些函式的使用方式。多載可自動推斷緩衝區長度 (因而不須指定大小引數)，也可以將不安全的舊函式自動取代成較新且安全的對應函式。 如需詳細資訊，請參閱[安全範本多載](../../c-runtime-library/secure-template-overloads.md)。

這些函式的 debug 程式庫版本會先以0xFE 填滿緩衝區。 若要停用此行為，請使用 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> 或 \<wchar.h>|

如需詳細的相容性資訊，請參閱 [Compatibility](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>範例

```C
// crt_makepath_s.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];
   errno_t err;

   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",
                      "crt_makepath_s", "c" );
   if (err != 0)
   {
      printf("Error creating path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,
                       _MAX_FNAME, ext, _MAX_EXT );
   if (err != 0)
   {
      printf("Error splitting the path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path extracted with _splitpath_s:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c

Path extracted with _splitpath_s:
   Drive: c:
   Dir: \sample\crt\
   Filename: crt_makepath_s
   Ext: .c
```

## <a name="see-also"></a>另請參閱

[檔案處理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s、_wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
