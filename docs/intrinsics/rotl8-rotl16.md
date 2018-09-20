---
title: _rotl8，_rotl16 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _rotl8
- _rotl16
dev_langs:
- C++
helpviewer_keywords:
- _rotl8 intrinsic
- _rotl16 intrinsic
ms.assetid: 8c519ab6-aef9-4f07-a387-daee8408368f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b70e3df22e4503d1e1a66d071c33aea7f2aef52
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412128"
---
# <a name="rotl8-rotl16"></a>_rotl8, _rotl16

**Microsoft 專屬**

將輸入值依指定的位置數目，向左旋轉至最高有效位元 (MSB)。

## <a name="syntax"></a>語法

```
unsigned char _rotl8( 
   unsigned char value, 
   unsigned char shift 
);
unsigned short _rotl16( 
   unsigned short value, 
   unsigned char shift 
);
```

#### <a name="parameters"></a>參數

*值*<br/>
[in]要旋轉的值。

*shift*<br/>
[in]若要旋轉的位元數。

## <a name="return-value"></a>傳回值

旋轉的值。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`_rotl8`|x86、 x64、 ARM|
|`_rotl16`|x86、 x64、 ARM|

**標頭檔** \<intrin.h >

## <a name="remarks"></a>備註

與左移位運算不同的是，執行左旋轉運算時，在高位階外的高位位元會移到最低有效位元位置。

## <a name="example"></a>範例

```
// rotl.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_rotl8, _rotl16)

int main()
{
    unsigned char c = 'A', c1, c2;

    for (int i = 0; i < 8; i++)
    {
       printf_s("Rotating 0x%x left by %d bits gives 0x%x\n", c,
               i, _rotl8(c, i));
    }

    unsigned short s = 0x12;
    int nBit = 10;

    printf_s("Rotating unsigned short 0x%x left by %d bits gives 0x%x\n",
            s, nBit, _rotl16(s, nBit));
}
```

```Output
Rotating 0x41 left by 0 bits gives 0x41
Rotating 0x41 left by 1 bits gives 0x82
Rotating 0x41 left by 2 bits gives 0x5
Rotating 0x41 left by 3 bits gives 0xa
Rotating 0x41 left by 4 bits gives 0x14
Rotating 0x41 left by 5 bits gives 0x28
Rotating 0x41 left by 6 bits gives 0x50
Rotating 0x41 left by 7 bits gives 0xa0
Rotating unsigned short 0x12 left by 10 bits gives 0x4800
```

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[_rotr8、_rotr16](../intrinsics/rotr8-rotr16.md)<br/>
[編譯器內建](../intrinsics/compiler-intrinsics.md)