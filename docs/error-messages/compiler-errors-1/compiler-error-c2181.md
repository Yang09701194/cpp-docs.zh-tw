---
title: 編譯器錯誤 C2181
ms.date: 11/04/2016
f1_keywords:
- C2181
helpviewer_keywords:
- C2181
ms.assetid: d52b2fe4-566a-40a9-b8e2-8dce1f287668
ms.openlocfilehash: a676794b5dedd17cfb973de36d3771ef1130a786
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527301"
---
# <a name="compiler-error-c2181"></a>編譯器錯誤 C2181

不合法的 else (沒有相符的 if)

每個 `else` 必須具有相符的 `if`。

下列範例會產生 C2181：

```
// C2181.cpp
int main() {
   int i = 0;
   else   // C2181
      i = 1;
}
```

可能的解決方式：

```
// C2181b.cpp
int main() {
   int i = 0;
   if(i)
      i = 0;
   else
      i = 1;
}
```