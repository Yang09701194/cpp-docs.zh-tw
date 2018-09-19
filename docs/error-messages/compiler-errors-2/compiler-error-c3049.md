---
title: 編譯器錯誤 C3049 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3049
dev_langs:
- C++
helpviewer_keywords:
- C3049
ms.assetid: 6ddf54f6-2c30-4d04-b637-98c6c922c533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8ba6878c893aeaaaa1f0851fc94a6fd13bbf104
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081243"
---
# <a name="compiler-error-c3049"></a>編譯器錯誤 C3049

'arg': OpenMP 'default' 子句中有無效的引數

已將不正確的值傳遞給 [default](../../parallel/openmp/reference/default-openmp.md) 子句。

下列範例會產生 C3049：

```
// C3049.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(private)   // C3049
   // try the following line instead
   // #pragma omp parallel default(shared)
   {
      ++n1;
   }
}
```