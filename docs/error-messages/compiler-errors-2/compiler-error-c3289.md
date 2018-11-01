---
title: 編譯器錯誤 C3289
ms.date: 11/04/2016
f1_keywords:
- C3289
helpviewer_keywords:
- C3289
ms.assetid: 3c1c623b-7fcf-43ab-a89a-8722532a8d29
ms.openlocfilehash: 0ebb56023694b1713bfe88379d07fc621da4d43f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622647"
---
# <a name="compiler-error-c3289"></a>編譯器錯誤 C3289

'property' : trivial 屬性不可索引

屬性宣告不正確。 必須定義索引屬性的存取子。 如需詳細資訊，請參閱 [property](../../windows/property-cpp-component-extensions.md) 。

## <a name="example"></a>範例

下列範例會產生 C3289。

```
// C3289.cpp
// compile with: /clr
public ref struct C {
   // user-defined simple indexer
   property int indexer1[int];   // C3289

   // user-defined indexer
   property int indexer2[int] {
      int get(int i) { return 0; }
      void set(int i, int j) {}
   }
};

int main() {
   C ^ MyC = gcnew C();
   MyC->indexer2[0] = 1;
}
```