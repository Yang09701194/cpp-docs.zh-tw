---
title: 編譯器錯誤 C2871
ms.date: 11/04/2016
f1_keywords:
- C2871
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
ms.openlocfilehash: 355a485de46916977be6f7b801794806a9c9e0ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165188"
---
# <a name="compiler-error-c2871"></a>編譯器錯誤 C2871

'name': 具有此名稱的命名空間不存在

當您傳遞不是命名空間的識別碼時，會發生此錯誤[使用](../../cpp/namespaces-cpp.md#using_directives)指示詞。

## <a name="example"></a>範例

下列範例會產生 C2871:

```cpp
// C2871.cpp
// compile with: /c
namespace a {
   int fn(int i) { return i; }
}
namespace b {
   using namespace d;   // C2871 because d is not a namespace
   using namespace a;   // OK
}
```