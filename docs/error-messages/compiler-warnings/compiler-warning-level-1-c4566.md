---
title: 編譯器警告 （層級 1） C4566 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4566
dev_langs:
- C++
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c25ff9d2a4c915570a28752d11778983f2cf2fc3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049172"
---
# <a name="compiler-warning-level-1-c4566"></a>編譯器警告 (層級 1) C4566

表示通用字元名稱 'char' 字元無法在目前的字碼頁 （頁面）

並非每個 Unicode 字元可以表示您目前的 ANSI 字碼頁中。

窄字串 （單一位元組字元） 會轉換成多位元組字元中，而不是寬字串 （雙位元組字元）。

下列範例會產生 C4566:

```
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```