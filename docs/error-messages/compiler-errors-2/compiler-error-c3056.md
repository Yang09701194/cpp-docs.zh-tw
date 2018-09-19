---
title: 編譯器錯誤 C3056 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3056
dev_langs:
- C++
helpviewer_keywords:
- C3056
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0495bc9c31df3aa3ff47ef860e8e47ea6f7c2248
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063576"
---
# <a name="compiler-error-c3056"></a>編譯器錯誤 C3056

'symbol': 符號和 'threadprivate' 指示詞不在同一個範圍內

[threadprivate](../../parallel/openmp/reference/threadprivate.md) 子句中所使用的符號必須與 `threadprivate` 子句位於相同的範圍中。

下列範例會產生 C3056：

```
// C3056.cpp
// compile with: /openmp
int x, y;
void test() {
   #pragma omp threadprivate(x, y)   // C3056
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

可能的解決方式：

```
// C3056b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)
void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```