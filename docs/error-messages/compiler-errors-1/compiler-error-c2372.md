---
title: 編譯器錯誤 C2372
ms.date: 11/04/2016
f1_keywords:
- C2372
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
ms.openlocfilehash: db13a6bc108588fbbd9c15e2bcc647bea073a333
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603459"
---
# <a name="compiler-error-c2372"></a>編譯器錯誤 C2372

'identifier': 重複定義;不同類型的間接取值

使用不同的衍生型別已定義的識別項。

下列範例會產生 C2326：

```
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```