---
title: 編譯器警告（層級3） C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: eb1d37d3b18563f6c443ae728318eeaf816e9353
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174150"
---
# <a name="compiler-warning-level-3-c4280"></a>編譯器警告（層級3） C4280

' operator-> ' 透過類型 ' type ' 進行自我遞迴

您的程式碼不正確地允許**operator->** 呼叫本身。

下列範例會產生 C4280：

```cpp
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```
