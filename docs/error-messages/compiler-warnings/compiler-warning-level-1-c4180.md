---
title: 編譯器警告 (層級 1) C4180
ms.date: 11/04/2016
f1_keywords:
- C4180
helpviewer_keywords:
- C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
ms.openlocfilehash: f542951424325db727fc6d4ba7ac449095bdac83
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175957"
---
# <a name="compiler-warning-level-1-c4180"></a>編譯器警告 (層級 1) C4180

套用至函式類型的限定詞沒有意義; 已忽略

限定詞 (例如 **const**) 套用至 `typedef`所定義的函式類型。

## <a name="example"></a>範例

```cpp
// C4180.cpp
// compile with: /W1 /c
typedef int FuncType(void);

// the const qualifier cannot be applied to the
// function type FuncType
const FuncType f;   // C4180
```
