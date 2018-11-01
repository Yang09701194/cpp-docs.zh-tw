---
title: 編譯器警告 (層級 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: 8eca942de1d2f78f5e42d4aac7e2441789a01862
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598896"
---
# <a name="compiler-warning-level-4-c4212"></a>編譯器警告 (層級 4) C4212

使用非標準擴充： 函式宣告使用省略符號

函式原型都有可變數目的引數。 函式定義則否。

下列範例會產生 C4212:

```
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```