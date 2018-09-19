---
title: 編譯器警告 （層級 1） C4533 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4533
dev_langs:
- C++
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a99211afe310730e9041f2f04dc8ce67a762ed0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084857"
---
# <a name="compiler-warning-level-1-c4533"></a>編譯器警告 (層級 1) C4533

'variable' 的初始化會略過 '指示'

在程式中的指示變更控制項的流程，使得初始化變數的指示，不會執行。 下列範例會產生 C4533:

```
// C4533.cpp
// compile with: /W1
#include <stdio.h>

struct A
{
   int m_data;
};

int main()
{
   if (1)
   {
      goto Label;
   }

   A a = { 100 };

   Label:   // C4533
      printf("\n%d", a.m_data);   // prints an uninitialized value
}
```