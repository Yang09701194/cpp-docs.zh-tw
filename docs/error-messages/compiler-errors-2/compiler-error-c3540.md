---
title: 編譯器錯誤 C3540
ms.date: 11/04/2016
f1_keywords:
- C3540
helpviewer_keywords:
- C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
ms.openlocfilehash: 94f35f9f3bf64e09087f28a11a4fb9802d9d3c0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761513"
---
# <a name="compiler-error-c3540"></a>編譯器錯誤 C3540

' type '： sizeof 無法套用至包含 ' auto ' 的類型

[Sizeof](../../cpp/sizeof-operator.md)運算子無法套用到指定的類型，因為它包含 `auto` 規範。

## <a name="example"></a>範例

下列範例會產生 C3540。

```cpp
// C3540.cpp
// Compile with /Zc:auto
int main() {
    auto x = 123;
    sizeof(x);    // OK
    sizeof(auto); // C3540
    return 0;
}
```

## <a name="see-also"></a>請參閱

[auto 關鍵字](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (推算變數類型)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof 運算子](../../cpp/sizeof-operator.md)
