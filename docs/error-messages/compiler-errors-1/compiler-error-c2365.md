---
title: 編譯器錯誤 C2365
ms.date: 11/04/2016
f1_keywords:
- C2365
helpviewer_keywords:
- C2365
ms.assetid: 35839b0b-4055-4b79-8957-b3a0871bdd02
ms.openlocfilehash: 9d862fb06041b01c306560264758d13f8f75b491
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611376"
---
# <a name="compiler-error-c2365"></a>編譯器錯誤 C2365

'class member': 重複定義，先前的定義是 'class member'

您嘗試要重新定義類別成員。

下列範例會產生 C2365。

```
// C2365.cpp
// compile with: /c
class C1 {
   int CFunc();
   char *CFunc;   // C2365, already exists as a member function

   int CMem;
   char *CMem();   // C2365, already exists as a data member
};
```