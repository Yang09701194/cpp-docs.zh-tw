---
title: 編譯器警告 （層級 4） C4932 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4932
dev_langs:
- C++
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c9143406fc4b52d50b5dc68215fa796f5100fb7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053917"
---
# <a name="compiler-warning-level-4-c4932"></a>編譯器警告 (層級 4) C4932

__identifier （identifier) 和\__identifier(identifier) 難以辨別是否

編譯器無法區分作為參數傳遞給 **__identifier** 的 `__finally` _finally `__try` 與 **或** 與 [_try](../../windows/identifier-cpp-cli.md)。 您不應該嘗試同時使用它們作為相同程式中的識別項，因為它會導致 [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) 錯誤。

下列範例會產生 C4932：

```
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```