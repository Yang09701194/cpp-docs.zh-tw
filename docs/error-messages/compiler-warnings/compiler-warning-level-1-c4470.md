---
title: 編譯器警告 (層級 1) C4470
ms.date: 11/04/2016
f1_keywords:
- C4470
helpviewer_keywords:
- C4470
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
ms.openlocfilehash: 7fd4644ab39e350c0c0badb527875b427a2c6987
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160896"
---
# <a name="compiler-warning-level-1-c4470"></a>編譯器警告 (層級 1) C4470

浮點控制 pragma 在 /clr 下會忽略

浮點控制 pragma 中：

- [fenv_access](../../preprocessor/fenv-access.md)

- [float_control](../../preprocessor/float-control.md)

- [fp_contract](../../preprocessor/fp-contract.md)

在不影響[/clr](../../build/reference/clr-common-language-runtime-compilation.md)。

下列範例會產生 C4470:

```
// C4470.cpp
// compile with: /clr /W1 /LD
#pragma float_control(except, on)   // C4470
```