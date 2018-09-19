---
title: 編譯器錯誤 C2203 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2203
dev_langs:
- C++
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6db497a7967e0cefc16ecb6e5a71874f86179b29
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053761"
---
# <a name="compiler-error-c2203"></a>編譯器錯誤 C2203

刪除操作員無法指定陣列的界限

具有 **/Za** (ANSI) 選項`delete`運算子可以刪除整個陣列，但沒有組件或特定成員的陣列。

下列範例會產生 C2203:

```
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```