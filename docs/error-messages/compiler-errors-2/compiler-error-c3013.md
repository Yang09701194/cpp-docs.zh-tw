---
title: 編譯器錯誤 C3013 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3013
dev_langs:
- C++
helpviewer_keywords:
- C3013
ms.assetid: f896777d-27e6-4b6d-baab-1567317f3374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4b605cdf090dea66507696f8ac7e9a00dce11c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049759"
---
# <a name="compiler-error-c3013"></a>編譯器錯誤 C3013

'clause' : 子句只能在 OpenMP 'directive' 指示詞上出現一次

某個子句在同一個指示詞上出現兩次。 請刪除其中一個子句。

下列範例會產生 C3013：

```
// C3013.cpp
// compile with: /openmp
int main() {
   int a, b, c, x, y, z;

   #pragma omp parallel shared(a,b,c) private(x)

   #pragma omp for nowait private(x) nowait   // C3013
   // The previous line generates C3013, with two nowait clauses
   // try the following line instead:
   // #pragma omp for nowait private(x)
   for (a = 0 ; a < 10 ; ++a) {
   }
}
```