---
title: 編譯器錯誤 C3408 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3408
dev_langs:
- C++
helpviewer_keywords:
- C3408
ms.assetid: 1f5ea979-fb1e-4214-b310-6fd6ca8249b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a9c73e09dff4a7d0c54e028f477b790bc565f1f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095179"
---
# <a name="compiler-error-c3408"></a>編譯器錯誤 C3408

'attribute': 屬性不能用於樣板定義上

無法將屬性套用至樣板定義。

## <a name="example"></a>範例

下列範例會產生 C3408。

```
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