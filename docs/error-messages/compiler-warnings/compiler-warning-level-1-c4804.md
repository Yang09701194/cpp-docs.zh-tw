---
title: 編譯器警告 (層級 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 3f1b349599c77bc001911431fe0d83496ca3dfce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199403"
---
# <a name="compiler-warning-level-1-c4804"></a>編譯器警告 (層級 1) C4804

' operation '：作業中不安全使用類型 ' bool '

當您以非預期的方式使用 `bool` 變數或值時，就會出現這個警告。 例如，如果您使用負一元運算子（ **-** ）或補數運算子（`~`）之類的運算子，則會產生 C4804。 編譯器會評估運算式。

## <a name="example"></a>範例

下列範例會產生 C4804：

```cpp
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```
