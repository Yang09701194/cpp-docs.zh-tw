---
title: 編譯器錯誤 C2599
ms.date: 11/04/2016
f1_keywords:
- C2599
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
ms.openlocfilehash: 872c3a66d4738c1a69990dffdbbc59cee9e90002
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544634"
---
# <a name="compiler-error-c2599"></a>編譯器錯誤 C2599

'enum': 不允許向前宣告列舉類型

編譯器不再支援受管理的列舉之向前宣告。

在不允許向前宣告列舉型別的[/Za](../../build/reference/za-ze-disable-language-extensions.md)。

下列範例會產生 C2599:

```
// C2599.cpp
// compile with: /clr /c
enum class Status;   // C2599

enum class Status2 { stop2, hold2, go2};

ref struct MyStruct {
   // Delete the following line to resolve.
   Status m_status;

   Status2 m_status2;   // OK
};

enum class Status { stop, hold, go };
```