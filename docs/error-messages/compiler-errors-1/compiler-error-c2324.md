---
title: 編譯器錯誤 C2324
ms.date: 11/04/2016
f1_keywords:
- C2324
helpviewer_keywords:
- C2324
ms.assetid: 215f0544-85b0-452d-825f-17a388b6a61c
ms.openlocfilehash: 924341d75c7126f8af30da1038781f9e559e9c2b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747887"
---
# <a name="compiler-error-c2324"></a>編譯器錯誤 C2324

' identifier '：不應出現在 ' name ' 的右邊

使用不正確的識別碼呼叫了析構函式。

下列範例會產生 C2324：

```cpp
// C2324.cpp
class A {};
typedef A* pA_t;
int i;

int main() {
   pA_t * ppa = new pA_t;
   ppa->~i;   // C2324
   ppa->~pA_t();   // OK
}
```
