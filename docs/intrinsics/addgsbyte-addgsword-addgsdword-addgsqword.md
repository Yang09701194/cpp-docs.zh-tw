---
title: __addgsbyte、__addgsword、__addgsdword、__addgsqword
ms.date: 09/02/2019
f1_keywords:
- __addgsdword
- __addgsqword
- __addgsword_cpp
- __addgsword
- __addgsbyte_cpp
- __addgsqword_cpp
- __addgsbyte
- __addgsdword_cpp
helpviewer_keywords:
- __addgsword intrinsic
- __addgsqword intrinsic
- __addgsdword intrinsic
- __addgsbyte intrinsic
ms.assetid: 4fa03e69-d849-49ed-ba37-1d3aa23c2a21
ms.openlocfilehash: 5dddd8b4a887dc0e01107f8c1036a399b4e52d2e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221089"
---
# <a name="__addgsbyte-__addgsword-__addgsdword-__addgsqword"></a>__addgsbyte、__addgsword、__addgsdword、__addgsqword

**Microsoft 專屬**

將值新增至相對於`GS`區段開頭之位移所指定的記憶體位置。

## <a name="syntax"></a>語法

```C
void __addgsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __addgsword(
   unsigned long Offset,
   unsigned short Data
);
void __addgsdword(
   unsigned long Offset,
   unsigned long Data
);
void __addgsqword(
   unsigned long Offset,
   unsigned __int64 Data
);
```

### <a name="parameters"></a>參數

*投影*\
在從開頭算起`GS`的位移。

*Data*\
在要加入至記憶體位置的值。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`__addgsbyte`|X64|
|`__addgsword`|X64|
|`__addgsdword`|X64|
|`__addgsqword`|X64|

**標頭檔**\<intrin.h. h >

## <a name="remarks"></a>備註

這些常式僅以內建函式的形式提供。

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[__incgsbyte、 \__incgsword、 \__incgsdword、 \__incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)\
[__readgsbyte、 \__readgsdword、 \__readgsqword、 \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)\
[__writegsbyte、 \__writegsdword、 \__writegsqword、 \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[編譯器內建函式](../intrinsics/compiler-intrinsics.md)
