---
title: 編譯器錯誤 C3137 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3137
dev_langs:
- C++
helpviewer_keywords:
- C3137
ms.assetid: 70bb1313-2e87-43ed-a0d8-33fa6ff475e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3c78ebb4f0c33424c823008c3afd8fb692a7086
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093671"
---
# <a name="compiler-error-c3137"></a>編譯器錯誤 C3137

'property': 無法初始化屬性

屬性無法初始化，例如，在建構函式的初始化清單中。

下列範例會產生 C3137:

```
// C3137.cpp
// compile with: /clr /c
ref class CMyClass {
public:
   property int Size {
      int get() {
         return 0;
      }
      void set( int i ) {}
   }

   CMyClass() : Size( 1 ) {   // C3137
      // to resolve this C3137, remove the initializer from the
      // ctor declaration and perform the assignment as follows
      // Size = 1;
   }
};
```
