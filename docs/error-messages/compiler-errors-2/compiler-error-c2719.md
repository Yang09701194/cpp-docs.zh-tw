---
title: 編譯器錯誤 C2719 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2719
dev_langs:
- C++
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4423352bad520d66920a01542f592ed8022482d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054178"
---
# <a name="compiler-error-c2719"></a>編譯器錯誤 C2719

'parameter'：具有 __declspec(align('#')) 的型式參數不會對齊

[對齊](../../cpp/align-cpp.md)`__declspec`函式參數，不允許修飾詞。 函式參數對齊可藉由所使用的呼叫慣例來控制。 如需詳細資訊，請參閱 <<c0> [ 呼叫慣例](../../cpp/calling-conventions.md)。

下列範例會產生 C2719，並說明如何加以修正：

```
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```