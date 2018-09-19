---
title: 編譯器警告 （層級 1） C4944 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4944
dev_langs:
- C++
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdf155ce5fb53bb4b1b5914d7738c8c12f458888
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105494"
---
# <a name="compiler-warning-level-1-c4944"></a>編譯器警告 (層級 1) C4944

'symbol': 無法從 'assembly1' 匯入符號：因為在目前的範圍中已經有 'symbol'

符號已定義於原始程式碼檔中，而 #using 陳述式已參考同時定義符號的組件。 會忽略組件中的符號。

## <a name="example"></a>範例

下列範例會建立具有 ClassA 類型的元件。

```
// C4944.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

## <a name="example"></a>範例

下列範例會產生 C4944。

```
// C4944b.cpp
// compile with: /clr /W1
class ClassA {
public:
   int u;
};

#using "C4944.dll"   // C4944 ClassA also defined C4944.dll

int main() {
   ClassA * x = new ClassA();
   x->u = 9;
   System::Console::WriteLine(x->u);
}
```