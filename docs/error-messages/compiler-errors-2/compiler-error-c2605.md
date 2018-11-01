---
title: 編譯器錯誤 C2605
ms.date: 11/04/2016
f1_keywords:
- C2605
helpviewer_keywords:
- C2605
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
ms.openlocfilehash: c1a3f1132edb90e119d97061fbbfb293d364ef3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676261"
---
# <a name="compiler-error-c2605"></a>編譯器錯誤 C2605

'name': 這個方法已保留在 Managed 或 WinRT 類別中

編譯器保留某些名稱供內部函式使用。  如需詳細資訊，請參閱 <<c0> [ 解構函式和完成項](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)。

## <a name="example"></a>範例

下列範例會產生 C2605：

```
// C2605.cpp
// compile with: /clr /c
ref class R {
protected:
   void Finalize() {}   // C2605
};
```