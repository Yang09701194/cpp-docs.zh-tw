---
title: _ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l
ms.date: 4/2/2020
api_name:
- _ismbcl2
- _ismbcl1
- _ismbcl0
- _ismbcl2_l
- _ismbcl1_l
- _ismbcl0_l
- _o__ismbcl0
- _o__ismbcl0_l
- _o__ismbcl1
- _o__ismbcl1_l
- _o__ismbcl2
- _o__ismbcl2_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ismbcl0
- _ismbcl1_l
- _ismbcl0
- ismbcl1
- ismbcl0_l
- _ismbcl2_l
- ismbcl2
- ismbcl1_l
- _ismbcl1
- _ismbcl0_l
- _ismbcl2
- ismbcl2_l
helpviewer_keywords:
- _ismbcl0_l function
- _ismbcl2 function
- _ismbcl1_l function
- ismbcl2 function
- _ismbcl1 function
- ismbcl0_l function
- ismbcl2_l function
- ismbcl1_l function
- ismbcl0 function
- ismbcl1 function
- _ismbcl2_l function
- _ismbcl0 function
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
ms.openlocfilehash: 813e6359d17f2ea4c6c0ded87a97c2afda243642
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919732"
---
# <a name="_ismbcl0-_ismbcl0_l-_ismbcl1-_ismbcl1_l-_ismbcl2-_ismbcl2_l"></a>_ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l

**字碼頁 932 特定函式**，使用目前的地區設定或指定的 LC_CTYPE 轉換狀態分類。

> [!IMPORTANT]
> 這個 API 不能用於在 Windows 執行階段中執行的應用程式。 如需詳細資訊，請參閱 [CRT functions not supported in Universal Windows Platform apps](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) (通用 Windows 平台應用程式中不支援的 CRT 函式)。

## <a name="syntax"></a>語法

```C
int _ismbcl0(
   unsigned int c
);
int _ismbcl0_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcl1(
   unsigned int c
);
int _ismbcl1_l(
   unsigned int c ,
   _locale_t locale
);
int _ismbcl2(
   unsigned int c
);
int _ismbcl2_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>參數

*c*<br/>
待測試字元。

*locale*<br/>
要使用的地區設定。

## <a name="return-value"></a>傳回值

如果字元符合測試條件，這些常式都會傳回非零值，如果不符合，則傳回 0。 如果*c* <= 255，而且有對應的 **_ismbb**常式（例如， **_ismbcalnum**對應至 **_ismbbalnum**），則結果會是對應之 **_ismbb**常式的傳回值。

## <a name="remarks"></a>備註

這些函式每一個都會測試指定的多位元組字元是否符合指定的條件。

輸出值會受到地區設定的 **LC_CTYPE** 分類設定影響；如需詳細資訊，請參閱 [setlocale](setlocale-wsetlocale.md)。 這些沒有 **_l** 尾碼的函式版本，會針對此與地區設定相關的行為使用目前的地區設定；具有 **_l** 尾碼的版本也一樣，只不過它們會改用傳遞的地區設定參數。 如需詳細資訊，請參閱 [Locale](../../c-runtime-library/locale.md)。

|常式傳回的值|測試條件 (限字碼頁 932)|
|-------------|-------------------------------------------|
|**_ismbcl0**|JIS 非漢字： 0x8140<=*c*<= 0x889E。|
|**_ismbcl0_l**|JIS 非漢字： 0x8140<=*c*<= 0x889E。|
|**_ismbcl1**|JIS 層級-1： 0X889f<<=*c*<= 0x9872。|
|**_ismbcl1_l**|JIS 層級-1： 0X889f<<=*c*<= 0x9872。|
|**_ismbcl2**|JIS 層級-2： 0X989f<<=*c*<= 0xEAA4。|
|**_ismbcl2_l**|JIS 層級-2： 0X989f<<=*c*<= 0xEAA4。|

函式會檢查指定的值*c*是否符合前述測試條件，但不會檢查*c*是否為有效的多位元組字元。 如果較低的位元組介於 0x00 - 0x3F、0x7F 或 0xFD - 0xFF 的範圍內，這些函式會傳回非零值，指出字元符合測試條件。 使用 [_ismbbtrail](ismbbtrail-ismbbtrail-l.md) 來測試是否已定義多位元組字元。

**結束特定字碼頁 932**

根據預設，此函式的全域狀態範圍設定為應用程式。 若要變更此項，請參閱[CRT 中的全域狀態](../global-state.md)。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**_ismbcl0**|\<mbstring.h>|
|**_ismbcl0_l**|\<mbstring.h>|
|**_ismbcl1**|\<mbstring.h>|
|**_ismbcl1_l**|\<mbstring.h>|
|**_ismbcl2**|\<mbstring.h>|
|**_ismbcl2_l**|\<mbstring.h>|

如需詳細的相容性資訊，請參閱 [Compatibility](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[字元分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 常式](../../c-runtime-library/ismbc-routines.md)<br/>
[is、isw 常式](../../c-runtime-library/is-isw-routines.md)<br/>
