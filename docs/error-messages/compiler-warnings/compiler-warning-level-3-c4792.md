---
title: 編譯器警告 （層級 3） C4792 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4792
dev_langs:
- C++
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4afb08cbe3203ff462f59fec4c1e712aa024c081
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136058"
---
# <a name="compiler-warning-level-3-c4792"></a>編譯器警告 (層級 3) C4792

使用 sysimport 宣告並從機器碼參考的函式 'function'; 匯入程式庫需要連結

已從 Unmanaged 函式呼叫使用 DllImport 匯入至程式的原生函式。 因此，您必須連結至 DLL 的匯入程式庫。

透過程式碼，或變更編譯方式，並無法解決這個警告。 請使用 [warning](../../preprocessor/warning.md) pragma 來停用這個警告。

下列範例會產生 C4792：

```
// C4792.cpp
// compile with: /clr /W3
// C4792 expected
using namespace System::Runtime::InteropServices;
[DllImport("msvcrt")]
extern "C" int __cdecl puts(const char *);
int main() {}

// Uncomment the following line to resolve.
// #pragma warning(disable : 4792)
#pragma unmanaged
void func(void){
   puts("test");
}
```