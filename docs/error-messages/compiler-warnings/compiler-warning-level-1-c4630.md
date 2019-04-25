---
title: 編譯器警告 (層級 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 98ea72bef0cb95163604144c1069a13c3b27d81c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324528"
---
# <a name="compiler-warning-level-1-c4630"></a>編譯器警告 (層級 1) C4630

'symbol': 'extern' 儲存類別規範不合法成員定義

資料成員或成員函式定義為`extern`。 成員不可以是外部，，雖然可以整個物件。 編譯器會忽略`extern`關鍵字。 下列範例會產生 C4630:

```
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```