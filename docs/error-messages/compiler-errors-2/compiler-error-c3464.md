---
title: 編譯器錯誤 C3464
ms.date: 11/04/2016
f1_keywords:
- C3464
helpviewer_keywords:
- C3464
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
ms.openlocfilehash: b21810d6df1fbfaf5ea94d9515487b16d00af548
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2019
ms.locfileid: "58775292"
---
# <a name="compiler-error-c3464"></a>編譯器錯誤 C3464

'type' 巢狀類型不可轉送

類型轉送未作用於巢狀類型上。

如需詳細資訊，請參閱 <<c0> [ 型別轉送 (C + + /cli CLI)](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="example"></a>範例

下列範例會建立元件。

```
// C3464.cpp
// compile with: /LD /clr
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>範例

下列範例會產生 C3464。

```
// C3464_b.cpp
// compile with: /clr /c
#using "C3464.dll"
[assembly:TypeForwardedTo(R::N::typeid)];   // C3464
[assembly:TypeForwardedTo(R::typeid)];   // OK
```