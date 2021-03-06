---
title: 編譯器錯誤 C3499
ms.date: 11/04/2016
f1_keywords:
- C3499
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
ms.openlocfilehash: e50aaeac4a9f02cf3e67c25a08afdc2df0f1c62f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738007"
---
# <a name="compiler-error-c3499"></a>編譯器錯誤 C3499

已被指定為具有 void 傳回類型的 Lambda 無法傳回值

當 Lambda 運算式指定 `void` 為傳回類型卻傳回值時；或 Lambda 運算式包含一個以上的陳述式並傳回值，卻未指定其傳回類型時，編譯器會產生此錯誤。

### <a name="to-correct-this-error"></a>若要改正這項錯誤

- 不要從 Lambda 運算式傳回值，或者，

- 提供 Lambda 運算式的傳回類型，或者，

- 將組成 Lambda 運算式主體的多個陳述式合併為單一陳述式。

## <a name="example"></a>範例

下列範例會產生 C3499，因為 Lambda 運算式的主體包含多個陳述式並傳回值，但 Lambda 運算式未指定傳回類型：

```cpp
// C3499a.cpp

int main()
{
   [](int x) { int n = x * 2; return n; } (5); // C3499
}
```

## <a name="example"></a>範例

下列範例顯示 C3499 的兩種可能解決方式。 第一個解決方式是提供 Lambda 運算式的傳回類型。 第二個解決方式是將組成 Lambda 運算式主體的多個陳述式合併為單一陳述式。

```cpp
// C3499b.cpp

int main()
{
   // Possible resolution 1:
   // Provide the return type of the lambda expression.
   [](int x) -> int { int n = x * 2; return n; } (5);

   // Possible resolution 2:
   // Combine the statements that make up the body of
   // the lambda expression into a single statement.
   [](int x) { return x * 2; } (5);
}
```

## <a name="see-also"></a>請參閱

[Lambda 運算式](../../cpp/lambda-expressions-in-cpp.md)
