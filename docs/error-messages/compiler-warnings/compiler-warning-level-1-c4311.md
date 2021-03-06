---
title: 編譯器警告 (層級 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: 52f8338423b5e3366b85207477b3b1ee5e9c399f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163098"
---
# <a name="compiler-warning-level-1-c4311"></a>編譯器警告 (層級 1) C4311

'variable' : 指標從 'type' 到 'type' 截斷

此警告會偵測 64 位元指標截斷問題。 例如，如果程式碼是針對 64 位元架構而編譯的，若指派給 `int` (32 位元)，指標 (64 位元) 的值將會被截斷。 如需詳細資訊，請參閱[使用指標的規則](/windows/win32/WinProg64/rules-for-using-pointers)。

如需警告 C4311 常見原因的詳細資訊，請參閱[常見的編譯器錯誤](/windows/win32/WinProg64/common-compiler-errors)。

下列程式碼範例會在針對 64 位元目標而編譯時產生 C4311，並接著示範如何修正此問題：

```cpp
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```
