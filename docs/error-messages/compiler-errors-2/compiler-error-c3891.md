---
title: 編譯器錯誤 C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: 74b8802a165ab3265cc0f1c6a0b33b31d3db401d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779163"
---
# <a name="compiler-error-c3891"></a>編譯器錯誤 C3891

'var': 常值資料成員不能做為左值

A[常值](../../extensions/literal-cpp-component-extensions.md)變數是常數，而且無法變更其值，在初始化之後，在宣告中。

下列範例會產生 C3891:

```
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```