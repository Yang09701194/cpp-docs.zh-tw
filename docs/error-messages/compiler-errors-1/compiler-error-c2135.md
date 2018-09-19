---
title: 編譯器錯誤 C2135 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2135
dev_langs:
- C++
helpviewer_keywords:
- C2135
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4945753bec1ab8d315c8f8028bf10513dcb21c1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070063"
---
# <a name="compiler-error-c2135"></a>編譯器錯誤 C2135

'bit operator': 不合法的位元欄位運算

傳址運算子 (`&`) 無法套用至位元欄位。

下列範例會產生 C2135：

```
// C2135.cpp
struct S {
   int i : 1;
};

struct T {
   int j;
};
int main() {
   &S::i;   // C2135 address of a bit field
   &T::j;   // OK
}
```