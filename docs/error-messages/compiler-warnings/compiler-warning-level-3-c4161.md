---
title: 編譯器警告 (層級 3) C4161
ms.date: 08/27/2018
f1_keywords:
- C4161
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
ms.openlocfilehash: e1bbc949c298a7cfb6c3a3a061616db3dc4730f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555827"
---
# <a name="compiler-warning-level-3-c4161"></a>編譯器警告 (層級 3) C4161

> #<a name="pragma-pragmapop--more-pops-than-pushes"></a>pragma *pragma*（pop...）： pop 數目比 push

## <a name="remarks"></a>備註

因為您原始程式碼針對 *pragma*所包含的 pop 數目比 push 多一個，所以堆疊可能無法如預期運作。 若要避免這個警告，請確定 pop 數目未超過 push 數目。

## <a name="example"></a>範例

下列範例會產生 C4161：

```cpp
// C4161.cpp
// compile with: /W3 /LD
#pragma pack(push, id)
#pragma pack(pop, id)
#pragma pack(pop, id)   // C4161, an extra pop

#pragma bss_seg(".my_data1")
int j;

#pragma bss_seg(push, stack1, ".my_data2")
int l;

#pragma bss_seg(pop, stack1)
int m;

#pragma bss_seg(pop, stack1)   // C4161
```