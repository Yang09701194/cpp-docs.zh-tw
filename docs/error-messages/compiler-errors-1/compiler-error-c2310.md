---
title: 編譯器錯誤 C2310
ms.date: 11/04/2016
f1_keywords:
- C2310
helpviewer_keywords:
- C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
ms.openlocfilehash: 8bd885a730bfe4890e99fa9ec7beb83169aca4d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302120"
---
# <a name="compiler-error-c2310"></a>編譯器錯誤 C2310

catch 處理常式必須指定一個類型

Catch 處理常式會指定沒有型別或多個型別。

下列範例會產生 C2310:

```
// C2310.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "Out of memory!";
   }
   catch( int ,int) {}   // C2310 two types
   // try the following line instead
   // catch( int)  {}
}
```