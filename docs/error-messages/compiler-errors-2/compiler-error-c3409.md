---
title: 編譯器錯誤 C3409
ms.date: 11/06/2018
f1_keywords:
- C3409
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
ms.openlocfilehash: 8ab2e0d152e4c123fa23512bc0111cebd070b3ee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200859"
---
# <a name="compiler-error-c3409"></a>編譯器錯誤 C3409

> 不允許空的屬性區塊

## <a name="remarks"></a>備註

編譯器將方括弧轉譯為[屬性](../../windows/attributes-alphabetical-reference.md)區塊，但找不到任何屬性。

當您使用方括弧做為 lambda 運算式定義的一部分時，編譯器可能會產生這個錯誤。 當編譯器無法判斷方括弧是否屬於 lambda 運算式或屬性區塊定義的一部分時，就會發生這個錯誤。 如需 Lambda 運算式的詳細資訊，請參閱 [Lambda 運算式](../../cpp/lambda-expressions-in-cpp.md)。

### <a name="to-correct-this-error"></a>若要改正這項錯誤

1. 如果方括弧屬於屬性區塊的一部分：

   1. 在屬性區塊中提供一或多個屬性。

   1. 移除屬性區塊。

1. 如果方括弧是 lambda 運算式的一部分，請確定 lambda 運算式遵循有效的語法規則。

   如需 lambda 運算式語法的詳細資訊，請參閱[Lambda 運算式語法](../../cpp/lambda-expression-syntax.md)。

## <a name="example"></a>範例

下列範例會產生 C3409。

```cpp
// C3409.cpp
// compile with: /c
#include <windows.h>
[]   // C3409
class a {};

// OK
[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface x {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class b : public x {};
```

## <a name="example"></a>範例

下列範例會產生 C3409，因為 lambda 運算式會使用 `mutable` 規格，但不會提供參數清單。 編譯器無法判斷方括弧是否為 lambda 運算式或屬性區塊定義的一部分。

```cpp
// C3409b.cpp

int main()
{
   [] mutable {}();
}
```

## <a name="see-also"></a>另請參閱

[attribute](../../windows/attributes-alphabetical-reference.md)<br/>
[Lambda 運算式](../../cpp/lambda-expressions-in-cpp.md)<br/>
[Lambda 運算式語法](../../cpp/lambda-expression-syntax.md)
