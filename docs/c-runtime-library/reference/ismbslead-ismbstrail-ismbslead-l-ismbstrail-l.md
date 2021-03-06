---
title: _ismbslead、_ismbstrail、_ismbslead_l、_ismbstrail_l
ms.date: 4/2/2020
api_name:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
- _o__ismbslead
- _o__ismbslead_l
- _o__ismbstrail
- _o__ismbstrail_l
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
- _ismbslead
- ismbs
- ismbslead_l
- _ismbs
- ismbstrail_l
- ismbslead
- _ismbstrail
- _ismbstrail_l
- ismbstrail
- _ismbslead_l
helpviewer_keywords:
- ismbstrail function
- _ismbslead function
- ismbslead function
- ismbslead_l function
- _ismbstrail function
- _ismbslead_l function
- ismbstrail_l function
- _ismbstrail_l function
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
ms.openlocfilehash: 892545ba0ac66604b0ea1c5adcfa32dd64b68973
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919165"
---
# <a name="_ismbslead-_ismbstrail-_ismbslead_l-_ismbstrail_l"></a>_ismbslead、_ismbstrail、_ismbslead_l、_ismbstrail_l

執行多位元組字元字串前導位元組和後隨位元組的即時線上測試，並判斷指定的子字串指標是否指向前導位元組或後隨位元組。

> [!IMPORTANT]
> 這個 API 不能用於在 Windows 執行階段中執行的應用程式。 如需詳細資訊，請參閱 [CRT functions not supported in Universal Windows Platform apps](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) (通用 Windows 平台應用程式中不支援的 CRT 函式)。

## <a name="syntax"></a>語法

```C
int _ismbslead(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbstrail(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbslead_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
int _ismbstrail_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>參數

*str*<br/>
指向字串開頭或先前已知的前導位元組之指標。

*目前*<br/>
在字串要進行測試的位置之指標。

*locale*<br/>
要使用的地區設定。

## <a name="return-value"></a>傳回值

如果字元是前導位元組， **_ismbslead**會傳回-1; 如果字元是尾位元組， **_ismbstrail**會傳回-1。 如果輸入字串有效，但不是前導位元組或後隨位元組，則這些函式會傳回零。 如果其中一個引數為**Null**，則會叫用不正確參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果允許繼續執行，這些函式會傳回**Null** ，並將**Errno**設為**EINVAL**。

## <a name="remarks"></a>備註

**_ismbslead**和 **_ismbstrail**的速度比 **_ismbblead**和 **_ismbbtrail**版本慢，因為它們會將字串內容納入考慮。

這些具有 **_l**尾碼的函式版本都相同，不同之處在于其地區設定相關行為會使用傳入的地區設定，而不是目前的地區設定。 如需詳細資訊，請參閱 [Locale](../../c-runtime-library/locale.md)。

根據預設，此函式的全域狀態範圍設定為應用程式。 若要變更此項，請參閱[CRT 中的全域狀態](../global-state.md)。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|選擇性標頭|
|-------------|---------------------|---------------------|
|**_ismbslead**|\<mbctype.h> 或 \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|
|**_ismbstrail**|\<mbctype.h> 或 \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|
|**_ismbslead_l**|\<mbctype.h> 或 \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|
|**_ismbstrail_l**|\<mbctype.h> 或 \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|

\* 針對此測試條件的資訊清單常數。

如需詳細的相容性資訊，請參閱 [Compatibility](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[字元分類](../../c-runtime-library/character-classification.md)<br/>
[_ismbc 常式](../../c-runtime-library/ismbc-routines.md)<br/>
[is、isw 常式](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb 常式](../../c-runtime-library/ismbb-routines.md)<br/>
