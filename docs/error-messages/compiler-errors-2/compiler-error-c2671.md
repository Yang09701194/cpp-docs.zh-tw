---
title: 編譯器錯誤 C2671 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2671
dev_langs:
- C++
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b37d9dc1e50da921bdbe758e73257100853517eb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026151"
---
# <a name="compiler-error-c2671"></a>編譯器錯誤 C2671

'function': 靜態成員函式沒有 'this' 指標

A`static`成員函式嘗試存取`this`。

下列範例會產生 C2671:

```
// C2671.cpp
struct S {
   static S* const func() { return this; }  // C2671
};
```