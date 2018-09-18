---
title: 編譯器警告 （層級 1） C4393 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4393
dev_langs:
- C++
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79a77e73e87d8ebc6a4bcff76fba296188233c1c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053852"
---
# <a name="compiler-warning-level-1-c4393"></a>編譯器警告 (層級 1) C4393

'var': const 對常值資料成員; 沒有任何作用已忽略

A[常值](../../windows/literal-cpp-component-extensions.md)也指定為 const 資料成員。  常值資料成員隱含 const，因為您不需要將 const 加入宣告。

下列範例會產生 C4393:

```
// C4393.cpp
// compile with: /clr /W1 /c
ref struct Y1 {
   literal const int staticConst = 10;   // C4393
   literal int staticConst2 = 10;   // OK
};
```