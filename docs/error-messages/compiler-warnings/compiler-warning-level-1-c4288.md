---
title: 編譯器警告 (層級 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: e706a448f4264eceedbb4fa8932c0fc30e88d532
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175736"
---
# <a name="compiler-warning-level-1-c4288"></a>編譯器警告 (層級 1) C4288

使用非標準的擴充： ' var '： for 迴圈中宣告的迴圈控制變數會在 for 迴圈範圍外使用;與外部範圍中的宣告衝突

以[/ze](../../build/reference/za-ze-disable-language-extensions.md)和 **/zc： forscope-** 編譯時，在**for 迴圈中**宣告的變數是在[for](../../cpp/for-statement-cpp.md)迴圈範圍之後使用。 C++語言的 Microsoft 擴充功能允許此變數保留在範圍內，而 C4288 會提醒您不會使用變數的第一個宣告。

如需如何使用/Ze 在**for**迴圈中指定 Microsoft 擴充功能的相關資訊，請參閱[/zc： forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)

下列範例會產生 C4288：

```cpp
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```
