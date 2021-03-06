---
title: 儲存類別指定名稱與函式宣告
ms.date: 11/04/2016
helpviewer_keywords:
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
ms.openlocfilehash: 69d6fa2b17523f2bb4068cd05a11265d91750021
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157874"
---
# <a name="storage-class-specifiers-with-function-declarations"></a>儲存類別指定名稱與函式宣告

您可以在函式宣告中使用 **static** 或 `extern` 儲存類別指定名稱。 函式一定會具有全域存留期。

**Microsoft 特定的**

內部層次的函式宣告與外部層次的函式宣告具有相同的意義。 這表示函式從其宣告的位置到轉譯單位的其餘部分皆可見，即使是在區域範圍宣告亦相同。

**結束 Microsoft 專有**

函式的可視性規則與變數的規則稍有不同，如下所示：

- 宣告為 **static** 的函式，只有在本身定義所在的原始程式檔中才可見。 位於相同原始程式檔中的函式可以呼叫 **static** 函式，不過，位於其他原始程式檔的函式則無法直接透過名稱存取該函式。 您可以在不同的原始程式檔中宣告另一個具有相同名稱的 **static** 函式，而不會發生衝突。

- 宣告為 `extern` 的函式在程式的所有原始程式檔中皆可見 (除非您稍後將這類函式重新宣告為 **static**)。 所有函式都可以呼叫 `extern` 函式。

- 省略儲存類別規範的函式宣告會預設為 `extern`。

**Microsoft 特定的**

Microsoft 允許將 `extern` 識別項重新定義為 **static**。

**結束 Microsoft 專有**

## <a name="see-also"></a>請參閱

[C 儲存類別](../c-language/c-storage-classes.md)
