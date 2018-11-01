---
title: 編譯器錯誤 C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: e9a998e1c3a6c2fb770fb9d26d97b8a24e5554d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432759"
---
# <a name="compiler-error-c3519"></a>編譯器錯誤 C3519

'invalid_param': 對 embedded_idl 屬性無效的參數

參數已傳遞給`embedded_idl`的屬性[#import](../../preprocessor/hash-import-directive-cpp.md)，但編譯器無法辨認的參數。

唯一允許的參數`embedded_idl`都`emitidl`和`no_emitidl`。

下列範例會產生 C3519:

```
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```