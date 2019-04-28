---
title: 編譯器錯誤 C2250
ms.date: 11/04/2016
f1_keywords:
- C2250
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
ms.openlocfilehash: ea426e071eecb09359c3a99a6f569f628595784a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301353"
---
# <a name="compiler-error-c2250"></a>編譯器錯誤 C2250

'identifier': 模稜兩可的 'class::member' 的繼承

在衍生的類別繼承虛擬基底類別虛擬函式的多個覆的寫。 這些覆寫會模稜兩可的衍生類別中。

下列範例會產生 C2286：

```
// C2250.cpp
// compile with: /c
// C2250 expected
struct V {
   virtual void vf();
};

struct A : virtual V {
   void vf();
};

struct B : virtual V {
   void vf();
};

struct D : A, B {
   // Uncomment the following line to resolve.
   // void vf();
};
```