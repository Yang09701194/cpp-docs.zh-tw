---
title: 編譯器錯誤 C3483
ms.date: 11/04/2016
f1_keywords:
- C3483
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
ms.openlocfilehash: 0d6c1467575e7fae7d5e4862f36e733a68210f8e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743090"
---
# <a name="compiler-error-c3483"></a>編譯器錯誤 C3483

'var' 已是 Lambda 擷取清單的一部分

您已多次傳遞相同的變數給 Lambda 運算式的擷取清單。

### <a name="to-correct-this-error"></a>若要改正這項錯誤

- 請從擷取清單移除變數的所有其他執行個體。

## <a name="example"></a>範例

下列範例會產生 C3483，因為 `n` 變數多次出現在 Lambda 運算式的擷取清單中：

```cpp
// C3483.cpp

int main()
{
   int m = 6, n = 5;
   [m,n,n] { return n + m; }(); // C3483
}
```

## <a name="see-also"></a>請參閱

[Lambda 運算式](../../cpp/lambda-expressions-in-cpp.md)
