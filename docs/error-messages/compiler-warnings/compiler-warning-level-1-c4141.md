---
title: 編譯器警告 (層級 1) C4141
ms.date: 11/04/2016
f1_keywords:
- C4141
helpviewer_keywords:
- C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
ms.openlocfilehash: 90128e5c306d87cb44b446d686d4df91c5735d90
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200092"
---
# <a name="compiler-warning-level-1-c4141"></a>編譯器警告 (層級 1) C4141

'modifier': 使用了一次以上

## <a name="example"></a>範例

```cpp
// C4141.cpp
// compile with: /W1 /LD
inline inline void func ();   // C4141
```
