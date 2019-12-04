---
title: 編譯器錯誤 C3142
ms.date: 11/04/2016
f1_keywords:
- C3142
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
ms.openlocfilehash: 2e23ab20cb147ea8113e1f92f8e24d55b72faa71
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746015"
---
# <a name="compiler-error-c3142"></a>編譯器錯誤 C3142

' property_name '：您無法接受屬性的位址

屬性的位址無法供開發人員使用。

下列範例會產生 C3142：

```cpp
// C3142_2.cpp
// compile with: /clr
using namespace System;
ref class CSize {
private:
   property int Size {
      int get();
   }
};

int main() {
    &CSize::Size; // C3142
}
```
