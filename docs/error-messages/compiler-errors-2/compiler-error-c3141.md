---
title: 編譯器錯誤 C3141
ms.date: 11/04/2016
f1_keywords:
- C3141
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
ms.openlocfilehash: 71f5a69bf96098b41bc2eb3945e1360955870657
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746184"
---
# <a name="compiler-error-c3141"></a>編譯器錯誤 C3141

' interface_name '：介面僅支援公用繼承

使用[介面（或 __interface）](../../cpp/interface.md)關鍵字定義的介面僅支援公用繼承。

下列範例會產生 C3141：

```cpp
// C3141.cpp
__interface IBase {};
__interface IDerived1 : protected IBase {};  // C3141
__interface IDerived2 : private IBase {};    // C3141
```
