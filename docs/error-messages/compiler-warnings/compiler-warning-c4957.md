---
title: 編譯器警告 C4957
ms.date: 11/04/2016
f1_keywords:
- C4957
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
ms.openlocfilehash: 340c26c97d0b5b686eee487cd3fd8b6b05bdf373
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164898"
---
# <a name="compiler-warning-c4957"></a>編譯器警告 C4957

> '*cast*'：從 '*cast_from*' 到 '*cast_to*' 的明確轉換無法驗證

## <a name="remarks"></a>備註

轉換會產生無法驗證的影像。

部分轉換是安全的 (例如，觸發使用者定義轉換的 `static_cast` 以及 `const_cast`)。 [safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) 保證會產生可驗證的程式碼。

如需詳細資訊，請參閱[單純和可C++驗證的程式碼（/cli）](../../dotnet/pure-and-verifiable-code-cpp-cli.md)。

**/Clr： safe**編譯器選項在 Visual Studio 2015 中已被取代，在 Visual Studio 2017 中不支援。

發出這個警告即表示發生錯誤，而且可以使用 [warning](../../preprocessor/warning.md) pragma 或 [/wd](../../build/reference/compiler-option-warning-level.md) 編譯器選項予以停用。

## <a name="example"></a>範例

下列範例會產生 C4957：

```cpp
// C4957.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4957 )
using namespace System;
int main() {
   Object ^ o = "Hello, World!";
   String ^ s = static_cast<String^>(o);   // C4957
   String ^ s2 = safe_cast<String^>(o);   // OK
}
```
