---
title: 編譯器錯誤 C2909
ms.date: 11/04/2016
f1_keywords:
- C2909
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
ms.openlocfilehash: 6c9a40bd271fa04146193e8315e205e293e8a34d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750477"
---
# <a name="compiler-error-c2909"></a>編譯器錯誤 C2909

'identifier': 函式樣板的明確具現化必須有傳回類型

函式樣板的明確具現化必須有其傳回類型的明確規格。 隱含傳回類型規格不適用。

下列範例會產生 C2909：

```cpp
// C2909.cpp
// compile with: /c
template<class T> int f(T);
template f<int>(int);         // C2909
template int f<int>(int);   // OK
```
