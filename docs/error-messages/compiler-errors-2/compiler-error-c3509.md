---
title: 編譯器錯誤 C3509
ms.date: 11/04/2016
f1_keywords:
- C3509
helpviewer_keywords:
- C3509
ms.assetid: cc2db39a-2f98-4e40-b803-496e585494e6
ms.openlocfilehash: e5e3c48581b5225bf1cf6777c9891c458034e11f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496634"
---
# <a name="compiler-error-c3509"></a>編譯器錯誤 C3509

'type': 無效的 Automation 傳回類型;當參數標示為 'retval'，傳回的型別必須是 'void'、 'HRESULT' 或 'SCODE'

中的 COM 介面的方法必須傳回 void 或的 HRESULT。

下列範例會產生 C3509:

```
// C3509.cpp
#define _ATL_DEBUG_QI

#define WIN32_LEAN_AND_MEAN   // Exclude rarely-used stuff from Windows headers
#define STRICT
#ifndef _WIN32_WINNT
#define _WIN32_WINNT 0x0400
#endif

#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
extern CComModule _Module;
#include <atlcom.h>
#include <atlctl.h>
#include <atlstr.h>

[module(name=oso)];

[dispinterface, uuid(00000000-0000-0000-0000-000000000001)]
__interface I {
   [id(1)] int f([out, retval] int*);   // C3509
   // try the following line instead
   // [id(1)] void f([out, retval] int*);
};

[coclass, uuid(00000000-0000-0000-0000-000000000002)]
struct C : I {
   int f(int*) {
   // try the following line instead, and delete return statement
   // void f(int*) {
      return 0;
   }
};

int main() {
}
```