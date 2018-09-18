---
title: 編譯器錯誤 C2798 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2798
dev_langs:
- C++
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88241989d54e1a068b226b59091a381f531dee9e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028853"
---
# <a name="compiler-error-c2798"></a>編譯器錯誤 C2798

'super::member' 模稜兩可

多重繼承的結構包含您參考具有成員[super](../../cpp/super.md)。 您可以透過下列方式修正錯誤：

- D.繼承清單中移除 B1 或 B2

- 變更 B1 B2 中的資料成員的名稱。

下列範例會產生 C2798:

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```