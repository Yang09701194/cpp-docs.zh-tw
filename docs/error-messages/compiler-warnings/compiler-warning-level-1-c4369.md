---
title: 編譯器警告 (層級 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: b0d99792e3e0ea372c8629319553dd9a59ad4b47
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187059"
---
# <a name="compiler-warning-level-1-c4369"></a>編譯器警告 (層級 1) C4369

' 枚舉器 '：列舉值 ' value ' 不能表示為 ' type '，值為 ' new_value '

列舉值的計算結果大於指定之基礎類型的最大值。  這會造成溢位，而編譯器會將列舉值包裝到類型的最小可能值。

## <a name="example"></a>範例

下列範例會產生 C4369。

```cpp
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```
