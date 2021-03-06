---
title: 編譯器錯誤 C3053
ms.date: 11/04/2016
f1_keywords:
- C3053
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
ms.openlocfilehash: 07514dfb931dcb5bf45bb8526cd19cf19103a56f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761200"
---
# <a name="compiler-error-c3053"></a>編譯器錯誤 C3053

'symbol': 'threadprivate' 只對全域或靜態資料項目有效

傳遞至 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 的符號必須是全域或靜態的。

下列範例會產生 C3053：

```cpp
// C3053.cpp
// compile with: /openmp
void Test() {
   int x, y;
   #pragma omp threadprivate(x, y)   // C3053
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

可能的解決方案：

```cpp
// C3053b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)

void Test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```
