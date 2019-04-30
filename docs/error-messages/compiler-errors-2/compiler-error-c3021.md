---
title: 編譯器錯誤 C3021
ms.date: 11/04/2016
f1_keywords:
- C3021
helpviewer_keywords:
- C3021
ms.assetid: 0cef6d97-e267-438a-ac8b-0daf5bbbc2cf
ms.openlocfilehash: 4863947fe2fedf9301fac302820cb69193581222
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386690"
---
# <a name="compiler-error-c3021"></a>編譯器錯誤 C3021

'arg' : OpenMP 指示詞 'directive' 上的引數是空的

OpenMP 指示詞需要有引數。

## <a name="example"></a>範例

下列範例會產生 C3021：

```
// C3021.cpp
// compile with: /openmp
#include <stdio.h>
#include "omp.h"

int g = 0;

int main()
{
    int x, y, i;

    #pragma omp parallel for schedule(static,)   // C3021
    for (i = 0; i < 10; ++i) ;

    #pragma omp parallel for schedule()   // C3021
    for (i = 0; i < 10; ++i)
        printf_s("Hello world, thread %d, iteration %d\n",
                 omp_get_thread_num(), i);

    #pragma omp parallel reduction()   // C3021
      ;

    #pragma omp parallel reduction(+ :)   // C3021
      ;

    //
    // The following shows correct syntax examples.
    //
    #pragma omp parallel reduction(+ : x, y)
      ;

    #pragma omp parallel reduction(* : x, y)
      ;

    #pragma omp parallel reduction(- : x, y)
      ;

    #pragma omp parallel reduction(& : x, y)
      ;

    #pragma omp parallel reduction(^ : x, y)
      ;

    #pragma omp parallel reduction(| : x, y)
      ;

    #pragma omp parallel reduction(&& : x, y)
      ;

    #pragma omp parallel reduction(|| : x, y)
      ;
}
```