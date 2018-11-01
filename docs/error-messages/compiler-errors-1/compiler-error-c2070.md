---
title: 編譯器錯誤 C2070
ms.date: 11/04/2016
f1_keywords:
- C2070
helpviewer_keywords:
- C2070
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
ms.openlocfilehash: 221b42e6425c84f4e34c99872fc0e51716e2db1b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581333"
---
# <a name="compiler-error-c2070"></a>編譯器錯誤 C2070

'type': 不合法的 sizeof 運算元

[Sizeof](../../cpp/sizeof-operator.md)運算子需要運算式或類型名稱。

下列範例會產生 C2070:

```
// C2070.cpp
void func() {}
int main() {
   int a;
   a = sizeof(func);   // C2070
}
```

可能的解決方式：

```
// C2070b.cpp
void func() {}
int main() {
   int a;
   a = sizeof(a);
}
```