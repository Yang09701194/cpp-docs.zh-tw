---
title: 編譯器錯誤 C2757 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2757
dev_langs:
- C++
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ff853ad499a9d50cc1c5c168ac13a570453dcba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058001"
---
# <a name="compiler-error-c2757"></a>編譯器錯誤 C2757

'symbol': 已經有同名的符號，因此無法使用此名稱做為命名空間名稱

因為命名空間識別項已在使用參考的組件中，目前編譯中所使用的符號。

下列範例會產生 C2757:

```
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

然後，

```
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
