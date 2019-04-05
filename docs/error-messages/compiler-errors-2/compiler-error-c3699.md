---
title: 編譯器錯誤 C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: 93058d34ca9a17ab175a55a7bc7b953d369e65c5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776735"
---
# <a name="compiler-error-c3699"></a>編譯器錯誤 C3699

'operator': 類型 'type' 上無法使用這個間接取值

嘗試使用不允許的間接取值`type`。

## <a name="example"></a>範例

下列範例會產生 C3699。

```
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

## <a name="example"></a>範例

Trivial 屬性不能有參考類型。 如需詳細資訊，請參閱 [property](../../extensions/property-cpp-component-extensions.md) 。 下列範例會產生 C3699。

```
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

## <a name="example"></a>範例

相當於"指標的指標 」 語法是追蹤參考的控制代碼。 下列範例會產生 C3699。

```
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```