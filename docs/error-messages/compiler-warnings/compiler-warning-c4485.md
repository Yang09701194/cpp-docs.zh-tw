---
title: 編譯器警告 C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: c92f805eb2960336ed34f5da93b6c13f46bf15ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165141"
---
# <a name="compiler-warning-c4485"></a>編譯器警告 C4485

' override_function '：符合基底 ref 類別方法 ' base_class_function '，但未標記為 ' new ' 或 ' override ';假設為 ' new ' （和 ' virtual '）

存取子會覆寫，包含或不含 `virtual` 關鍵字、基類存取子函式，但 `override` 或 `new` 規範不屬於覆寫函式簽章的一部分。 新增 `new` 或 `override` 規範，以解決這個警告。

如需詳細資訊，請參閱[override](../../extensions/override-cpp-component-extensions.md)和[new （vtable 中的新位置）](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) 。

C4485 一律會發出為錯誤。 請使用[warning](../../preprocessor/warning.md) pragma 來隱藏 C4485。

## <a name="example"></a>範例

下列範例會產生 C4485

```cpp
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```
