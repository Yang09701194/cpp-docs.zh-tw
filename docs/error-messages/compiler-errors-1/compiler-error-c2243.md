---
title: 編譯器錯誤 C2243
ms.date: 11/04/2016
f1_keywords:
- C2243
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
ms.openlocfilehash: f5a62b1c12b94735d0383697bf7a92d12d64b21f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757796"
---
# <a name="compiler-error-c2243"></a>編譯器錯誤 C2243

'conversion type' 從 'type1' 至 'type2' 的轉換已經存在，但無法存取

存取保護 (`protected` 或 `private`) 會防止從衍生類別的指標轉換為基底類別的指標。

下列範例會產生 C2243：

```cpp
// C2243.cpp
// compile with: /c
class B {};
class D : private B {};
class E : public B {};

D d;
B *p = &d;   // C2243

E e;
B *p2 = &e;
```

`protected` 或 `private` 存取的基底類別無法供衍生類別的用戶端存取。 這些層級的存取控制是用來指出基底類別是用戶端應該看到的實作細節。 如果您希望衍生類別的用戶端可以存取衍生類別指標對基底類別指標的隱含轉換，請使用公用衍生。
