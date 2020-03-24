---
title: 編譯器警告 (層級 1) C4384
ms.date: 11/04/2016
f1_keywords:
- C4384
helpviewer_keywords:
- C4384
ms.assetid: fafa8eb2-cbfc-4edb-8b0f-511ff5d37ac0
ms.openlocfilehash: 650f722affb6f1fe8c51e7a93619ecdef077fdb6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186955"
---
# <a name="compiler-warning-level-1-c4384"></a>編譯器警告 (層級 1) C4384

\#pragma ' make_public ' 只應用於全域範圍

未正確套用[make_public](../../preprocessor/make-public.md) pragma。

## <a name="example"></a>範例

下列範例會產生 C4384。

```cpp
// C4384.cpp
// compile with: /c /W1
namespace n {
   #pragma make_public(N::C)   // C4384
   namespace N {
      class C {};
   }
}
```
