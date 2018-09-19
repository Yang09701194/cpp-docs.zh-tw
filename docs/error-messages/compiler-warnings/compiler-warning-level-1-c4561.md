---
title: 編譯器警告 （層級 1） C4561 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4561
dev_langs:
- C++
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ba0770a8b8b42c8174d421f55dd45ff7f335d06
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115784"
---
# <a name="compiler-warning-level-1-c4561"></a>編譯器警告 (層級 1) C4561

'__fastcall' 不具有 '/ /clr' 選項： 將轉換成 '\__stdcall'

[__Fastcall](../../cpp/fastcall.md)函式呼叫慣例不能搭配[/clr](../../build/reference/clr-common-language-runtime-compilation.md)編譯器選項。 編譯器會忽略呼叫`__fastcall`。 若要修正這個警告，移除對 **__fastcall**或編譯而不要 **/clr**。

下列範例會產生 C4561:

```
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```