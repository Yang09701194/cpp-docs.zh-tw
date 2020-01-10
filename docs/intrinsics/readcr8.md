---
title: __readcr8
ms.date: 09/02/2019
f1_keywords:
- __readcr8
helpviewer_keywords:
- __readcr8 intrinsic
ms.assetid: fce16953-87ff-4fbe-8081-7962b97ae46c
ms.openlocfilehash: 525775fde4cb96cecfcabef878780d5a2aa6743a
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221240"
---
# <a name="__readcr8"></a>__readcr8

**Microsoft 專屬**

讀取 CR8 暫存器, 並傳回其值。

## <a name="syntax"></a>語法

```C
unsigned __int64 __readcr8(void);
```

## <a name="return-value"></a>傳回值

CR8 暫存器中的值。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`__readcr8`|X64|

**標頭檔**\<intrin.h. h >

## <a name="remarks"></a>備註

內建函式僅適用于核心模式, 而常式僅以內建函式的形式提供。

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[編譯器內建函式](../intrinsics/compiler-intrinsics.md)
