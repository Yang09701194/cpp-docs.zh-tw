---
title: fwide
ms.date: 11/04/2016
api_name:
- fwide
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fwide
helpviewer_keywords:
- fwide function
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
ms.openlocfilehash: 652aee03bfb5504a51d74efb326cc7a3d7c28649
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171199"
---
# <a name="fwide"></a>fwide

未實作。

## <a name="syntax"></a>語法

```C
int fwide(
   FILE *stream,
   int mode;
);
```

### <a name="parameters"></a>參數

*stream*<br/>
檔案結構**的**指標（已忽略）。

*mode*<br/>
資料流的新寬度︰寬字元為正值、位元組為負值、零則保留不變。 (這個值會被忽略。)

## <a name="return-value"></a>傳回值

此函式目前只會傳回*模式*。

## <a name="remarks"></a>備註

此函式的目前版本不符合標準。

## <a name="requirements"></a>需求

|函數|必要的標頭|
|--------------|---------------------|
|**fwide**|\<wchar.h>|

如需詳細資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。
