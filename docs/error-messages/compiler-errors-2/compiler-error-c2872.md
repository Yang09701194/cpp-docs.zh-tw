---
title: 編譯器錯誤 C2872
ms.date: 11/04/2016
f1_keywords:
- C2872
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
ms.openlocfilehash: 103998c7872b683c7405796ee28bd550246ae9bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257605"
---
# <a name="compiler-error-c2872"></a>編譯器錯誤 C2872

'*符號*': 模稜兩可的符號

編譯器無法判斷在參考的符號。 具有指定名稱的多個符號位於範圍內。 請參閱下列的檔案位置和宣告的錯誤訊息的附註編譯器發現模稜兩可的符號。 若要修正此問題，您可以完整限定的模稜兩可的符號使用它的命名空間，例如`std::byte`或`::byte`。 您也可以使用[命名空間別名](../../cpp/namespaces-cpp.md#namespace_aliases)釐清您的程式碼中的符號的使用者內含的命名空間提供方便的簡短名稱，供使用。

如果包含的標頭檔，就會發生 C2872 [using 指示詞](../../cpp/namespaces-cpp.md#using_directives)，和後續的標頭檔會包含在所包含的類型，也是在指定的命名空間中`using`指示詞。 指定`using`指示詞只是在所有標頭檔案由指定之後`#include`。

C2872 之間發生衝突，因此，可以發生在 Visual Studio 2013`Windows::Foundation::Metadata::Platform`列舉型別和C++/CX 定義`Platform`命名空間。 若要解決此問題，請遵循下列步驟：

- 移除專案檔中的"using 命名空間 Windows::Foundation::Metadata"子句。

- 指定包含此命名空間中的任何類型的完整的名稱。

## <a name="example"></a>範例

下列範例會產生 C2872，因為模稜兩可的參考對變數，名為`i`; 兩個具有相同名稱的變數是在範圍內：

```cpp
// C2872.cpp
// compile with: cl /EHsc C2872.cpp
namespace A {
   int i;
}

using namespace A;
int i;
int main() {
   ::i++;   // ok, uses i from global namespace
   A::i++;   // ok, uses i from namespace A
   i++;   // C2872 ambiguous: ::i or A::i?
   // To fix this issue, use the fully qualified name
   // for the intended variable.
}
```
