---
title: 編譯器警告 （層級 1） C4003 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4003
dev_langs:
- C++
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2c6d281f4a5e7f59e0e7a34fb77d2d18b295e7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029893"
---
# <a name="compiler-warning-level-1-c4003"></a>編譯器警告 （層級 1） C4003

巨集 'identifier' 的實質參數不足

在巨集定義的型式參數的數目超過巨集中的實際參數數目。 巨集展開替代遺漏參數的空白文字。

下列範例會產生 C4003:

```
// C4003.cpp
// compile with: /WX
#define test(a,b) (a+b)

int main()
{
   int a = 1;
   int b = 2;
   a = test(b);   // C4003
   // try..
   a = test(a,b);
}
```