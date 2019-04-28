---
title: 編譯器錯誤 C2137
ms.date: 11/04/2016
f1_keywords:
- C2137
helpviewer_keywords:
- C2137
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
ms.openlocfilehash: 7051fbe788790f1e91a3f54720f72d8370d1e9a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350617"
---
# <a name="compiler-error-c2137"></a>編譯器錯誤 C2137

空白的字元常數

不允許空白的字元常數 ( ' ' )。

下列範例會產生 C2137：

```
// C2137.cpp
int main() {
   char c = '';   // C2137
   char d = ' ';   // OK
}
```