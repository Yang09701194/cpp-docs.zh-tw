---
title: 編譯器錯誤 C3408
ms.date: 11/04/2016
f1_keywords:
- C3408
helpviewer_keywords:
- C3408
ms.assetid: 1f5ea979-fb1e-4214-b310-6fd6ca8249b1
ms.openlocfilehash: 8c606ceb446cdf1e6bc6df52853b8d590751eb21
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760695"
---
# <a name="compiler-error-c3408"></a>編譯器錯誤 C3408

'attribute': 屬性不能用於樣板定義上

無法將屬性套用至樣板定義。

## <a name="example"></a>範例

下列範例會產生 C3408。

```cpp
// C3408.cpp
// compile with: /c
template <class T> struct PTS {
   enum {
      IsPointer = 0,
      IsPointerToDataMember = 0
   };
};

template <class T>
[coclass]   // C3408
struct PTS<T*> {
   enum {
      IsPointer = 1,
      IsPointerToDataMember = 0
   };
};

template
<class T, class U>
struct PTS<T U::*> {
   enum {
      IsPointer = 1,
      IsPointerToDataMember = 1
   };
};

struct S{};

extern "C" int printf(const char*,...);

int main() {
   S s, *pS;
   int S::*ptm;

   printf("PTS<S>::IsPointer == %d PTS<S>::IsPointerToDataMember == %d\n", PTS<S>::IsPointer, PTS<S>:: IsPointerToDataMember);
   printf("PTS<S*>::IsPointer == %d PTS<S*>::IsPointerToDataMember == %d\n", PTS<S*>::IsPointer, PTS<S*>:: IsPointerToDataMember);
   printf("PTS<int S::*>::IsPointer == %d PTS<int S::*>::IsPointerToDataMember == %d\n", PTS<int S::*>::IsPointer, PTS<int S::*>:: IsPointerToDataMember);
}
```
