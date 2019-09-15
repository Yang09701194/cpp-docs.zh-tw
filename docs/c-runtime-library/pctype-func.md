---
title: __pctype_func
ms.date: 11/04/2016
api_name:
- __pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: f5dae74dd601df1dc737293a181eca60f5cd23f8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944033"
---
# <a name="__pctype_func"></a>__pctype_func

擷取字元分類資訊陣列的指標。

## <a name="syntax"></a>語法

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>傳回值

字元分類資訊陣列的指標。

## <a name="remarks"></a>備註

字元分類表中的資訊僅供內部使用，且由分類 `char` 類型字元的各種函式使用。 如需詳細資訊，請參閱 [_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md) 的 `Remarks` 節。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|__pctype_func|ctype.h|

## <a name="see-also"></a>另請參閱

[_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
