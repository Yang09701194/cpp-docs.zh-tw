---
title: 編譯器警告 (層級 4) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: b9083670465d68493d90a8e96ff7ee5db34c1978
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991319"
---
# <a name="compiler-warning-level-4-c4289"></a>編譯器警告 (層級 4) C4289

使用非標準的擴充：'var' : 在 for-loop 範圍外使用 for-loop 中所宣告的迴圈控制變數

以[/ze](../../build/reference/za-ze-disable-language-extensions.md)和 **/zc： forScope-** 編譯時，在[for 迴圈中](../../cpp/for-statement-cpp.md)宣告的變數是在**for**迴圈範圍之後使用。

如需如何在**for**迴圈中使用 **/ze**指定標準行為的詳細資訊，請參閱[/zc： forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 。

此警告預設為關閉。 如需詳細資訊，請參閱 [預設為關閉的編譯器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 。

下列範例會產生 C4289：

```cpp
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```
