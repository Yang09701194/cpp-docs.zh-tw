---
title: 編譯器錯誤 C3853 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3853
dev_langs:
- C++
helpviewer_keywords:
- C3853
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a347321b8c7884381fc57412d18422d7993d2f22
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021625"
---
# <a name="compiler-error-c3853"></a>編譯器錯誤 C3853

'=': 重新初始化參考或指派透過函式參考是不合法

無法指派給透過函式的參考，因為函式都不是左值。

下列範例會產生 C3853:

```
// C3853.cpp
// compile with: /EHsc
#include <iostream>
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   rf = afunc;   // C3853, can't reassign to a ref that's an lvalue
   int i = 99;
   int & ri = i;
   std::cout << i << std::endl;
   ri = 0;   // OK, i = 88;
   std::cout << i << std::endl;
}
```