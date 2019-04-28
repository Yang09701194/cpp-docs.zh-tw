---
title: 編譯器錯誤 C2373
ms.date: 11/04/2016
f1_keywords:
- C2373
helpviewer_keywords:
- C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
ms.openlocfilehash: 967bdec10e0e1c04083770d52da930837d8eeb7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339074"
---
# <a name="compiler-error-c2373"></a>編譯器錯誤 C2373

'identifier' : 重複定義; 類型修飾詞不相同

已使用不同的類型修飾詞定義識別項。

下列範例會產生 C2373：

```
// C2373.h
void __clrcall func( void );
const int i = 20;
```

然後：

```
// C2373.cpp
// compile with: /c
#include "C2373.h"
extern void __cdecl func( void );   // C2373
extern void __clrcall func( void );   // OK

extern int i;   // C2373
extern const int i;   // OK
```