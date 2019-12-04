---
title: 編譯器錯誤 C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 8a12bdfaf0931fb0a94dafc289f9ae39aef61f23
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757227"
---
# <a name="compiler-error-c3765"></a>編譯器錯誤 C3765

' event '：無法在標記為 event_receiver 的類別/結構 ' type ' 中定義事件

如果類別標記為[event_receiver](../../windows/event-receiver.md)屬性，則類別不能包含[__event](../../cpp/event.md)宣告。

下列範例會產生 C3765：

```cpp
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```
