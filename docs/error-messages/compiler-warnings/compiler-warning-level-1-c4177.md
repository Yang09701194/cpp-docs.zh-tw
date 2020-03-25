---
title: 編譯器警告 (層級 1) C4177
ms.date: 11/04/2016
f1_keywords:
- C4177
helpviewer_keywords:
- C4177
ms.assetid: 2b05a5b3-696e-4f21-818e-227b9335e748
ms.openlocfilehash: fd7e4bc42b38b335585a3f057aef521b5cf76b05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199949"
---
# <a name="compiler-warning-level-1-c4177"></a>編譯器警告 (層級 1) C4177

\#pragma pragma 應位於全域範圍

[pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) pragma 不應該用在區域範圍內。 在目前範圍後，直到遇到全域範圍之前， **pragma** 都是無效的。

下列範例會產生 C4177：

```cpp
// C4177.cpp
// compile with: /W1
// #pragma bss_seg("global")   // OK

int main() {
   #pragma bss_seg("local")    // C4177
}
```
