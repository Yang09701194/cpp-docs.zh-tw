---
title: 編譯器錯誤 C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 345cdd17b9da0be8f8d6e9f7b5f48624ade412bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761578"
---
# <a name="compiler-error-c3075"></a>編譯器錯誤 C3075

'instance' : 不可將參考類型的執行個體 'type' 嵌入實值類型中

實值類型不能包含參考類型的執行個體。

如需詳細資訊，請參閱[ C++參考型別的堆疊語義](../../dotnet/cpp-stack-semantics-for-reference-types.md)。

## <a name="example"></a>範例

下列範例會產生 C3075。

```cpp
// C3075.cpp
// compile with: /clr /c
ref struct U {};
value struct X {
   U y;   // C3075
};

ref struct Y {
   U y;   // OK
};
```
