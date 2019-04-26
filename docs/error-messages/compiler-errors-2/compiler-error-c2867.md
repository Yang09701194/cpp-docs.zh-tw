---
title: 編譯器錯誤 C2867
ms.date: 11/04/2016
f1_keywords:
- C2867
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
ms.openlocfilehash: 3c79fec9f52ea9451cea456dcc062af9bcbe9b3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164965"
---
# <a name="compiler-error-c2867"></a>編譯器錯誤 C2867

'identifier': 不是命名空間

A`using`指示詞會套用至命名空間以外的項目。

下列範例會產生 C2867:

```
// C2867.cpp
// compile with: /c
namespace N {
   class X {};
}
using namespace N::X;   // C2867
```