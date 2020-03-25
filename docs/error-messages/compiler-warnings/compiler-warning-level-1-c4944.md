---
title: 編譯器警告 (層級 1) C4944
ms.date: 11/04/2016
f1_keywords:
- C4944
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
ms.openlocfilehash: f9db36d52647b55c292a15ca724822f8b8b47e9c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199196"
---
# <a name="compiler-warning-level-1-c4944"></a>編譯器警告 (層級 1) C4944

'symbol': 無法從 'assembly1' 匯入符號：因為在目前的範圍中已經有 'symbol'

符號已定義於原始程式碼檔中，而 #using 陳述式已參考同時定義符號的組件。 會忽略組件中的符號。

## <a name="example"></a>範例

下列範例會建立具有 ClassA 類型的元件。

```csharp
// C4944.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

## <a name="example"></a>範例

下列範例會產生 C4944。

```cpp
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
