---
title: 編譯器錯誤 C2630
ms.date: 11/04/2016
f1_keywords:
- C2630
helpviewer_keywords:
- C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
ms.openlocfilehash: 5636b17573cd89c5a32e328aa3800d71136b84fc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754702"
---
# <a name="compiler-error-c2630"></a>編譯器錯誤 C2630

在應該是以逗號分隔的清單中找到 ' symbol '

符號會出現在需要逗號的內容中。

下列範例會產生 C2630：

```cpp
// C2630.cpp
// compile with: /c
struct D {
   D(int);
};

struct E {
   E(int);
};

class C : public D, public E {
   C();
};

C::C() : D(0) ; E(0) { }   // C2630
C::C() : D(0), E(0) {}   // OK
```
