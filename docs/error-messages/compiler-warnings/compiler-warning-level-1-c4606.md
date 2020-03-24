---
title: 編譯器警告 (層級 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: 9b38e9670157fd15dc7c4b6a96ced7ad40c43e34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185993"
---
# <a name="compiler-warning-level-1-c4606"></a>編譯器警告 (層級 1) C4606

\#pragma 警告：已忽略 ' warning_number ';程式碼分析警告未與警告層級相關聯

針對程式碼分析警告，[警告](../../preprocessor/warning.md)pragma 僅支援 `error`、`once`和 `default`。

## <a name="example"></a>範例

下列範例會產生 C4606。

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
