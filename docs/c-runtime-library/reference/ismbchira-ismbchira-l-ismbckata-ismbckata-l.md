---
title: _ismbchira、_ismbchira_l、_ismbckata、_ismbckata_l
ms.date: 4/2/2020
api_name:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
- _o__ismbchira
- _o__ismbchira_l
- _o__ismbckata
- _o__ismbckata_l
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
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
ms.openlocfilehash: 89c6aacbb6726165703d38e3ea519806b1f970d2
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910700"
---
# <a name="_ismbchira-_ismbchira_l-_ismbckata-_ismbckata_l"></a>_ismbchira、_ismbchira_l、_ismbckata、_ismbckata_l

**字碼頁 932 特定函式**

> [!IMPORTANT]
> 這個 API 不能用於在 Windows 執行階段中執行的應用程式。 如需詳細資訊，請參閱 [CRT functions not supported in Universal Windows Platform apps](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) (通用 Windows 平台應用程式中不支援的 CRT 函式)。

## <a name="syntax"></a>語法

```C
int _ismbchira(
   unsigned int c
);
int _ismbchira_l(
   unsigned int c,
   _locale_t locale
);
int _ismbckata(
   unsigned int c
);
int _ismbckata_l(
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

這些具有 **_l**尾碼的函式版本都相同，不同之處在于它們會使用傳入的地區設定，而非目前的地區設定來處理其地區設定相關的行為。 如需詳細資訊，請參閱 [Locale](../../c-runtime-library/locale.md)。

|常式傳回的值|測試條件 (限字碼頁 932)|
|-------------|-------------------------------------------|
|**_ismbchira**|雙位元組平假名： 0X829f<<=*c*<= 0x82F1。|
|**_ismbchira_l**|雙位元組平假名： 0X829f<<=*c*<= 0x82F1。|
|**_ismbckata**|雙位元組片假名： 0x8340<<=*c*<= 0x8396。|
|**_ismbckata_l**|雙位元組片假名： 0x8340<<=*c*<= 0x8396。|

**結束特定字碼頁 932**

根據預設，此函式的全域狀態範圍設定為應用程式。 若要變更此項，請參閱[CRT 中的全域狀態](../global-state.md)。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**_ismbchira**|\<mbstring.h>|
|**_ismbchira_l**|\<mbstring.h>|
|**_ismbckata**|\<mbstring.h>|
|**_ismbckata_l**|\<mbstring.h>|

如需詳細的相容性資訊，請參閱 [Compatibility](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[字元分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 常式](../../c-runtime-library/ismbc-routines.md)<br/>
[is、isw 常式](../../c-runtime-library/is-isw-routines.md)<br/>
[語言](../../c-runtime-library/locale.md)<br/>
[多位元組字元序列的解譯](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
