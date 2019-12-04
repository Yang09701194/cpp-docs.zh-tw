---
title: 編譯器錯誤 C3046
ms.date: 11/04/2016
f1_keywords:
- C3046
helpviewer_keywords:
- C3046
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
ms.openlocfilehash: d4af29ff6a5267dc80c52e8a3ea9d92cad8d8f7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761334"
---
# <a name="compiler-error-c3046"></a>編譯器錯誤 C3046

OpenMP '#pragma omp sections' 區域中遺漏結構化區塊

[sections](../../parallel/openmp/reference/sections-openmp.md) 指示詞具有空的程式碼區塊。

下列範例會產生 C3046：

```cpp
// C3046.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
/*
         ++n2;

         #pragma omp section
         {
            ++n3;
         }
*/
       }   // C3046 uncomment code to resolve this C3046
   }
}
```
