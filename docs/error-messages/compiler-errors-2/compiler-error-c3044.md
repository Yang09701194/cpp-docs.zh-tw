---
title: 編譯器錯誤 C3044
ms.date: 11/04/2016
f1_keywords:
- C3044
helpviewer_keywords:
- C3044
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
ms.openlocfilehash: 74e931d8110c1104125b977e45ad0c6fd3ffd5f0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761360"
---
# <a name="compiler-error-c3044"></a>編譯器錯誤 C3044

'section' : 只允許以巢狀方式直接放在 OpenMP 'sections' 指示詞之下

編譯器發現 `section` 指示詞的使用方式錯誤。 如需詳細資訊，請參閱 [章節](../../parallel/openmp/reference/sections-openmp.md)。

下列範例會產生 C3044：

```cpp
// C3044.cpp
// compile with: /openmp /c
#include "omp.h"
int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
         ++n2;
      }

      #pragma omp section   // C3044
      {
         ++n3;
      }
   }

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
         #pragma omp section   // OK
         {
            ++n3;
         }
      }
   }
}
```
