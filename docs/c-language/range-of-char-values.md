---
title: char 值的範圍
ms.date: 11/04/2016
ms.assetid: 15ae9781-ec21-4333-bba8-6d2383bbf7f1
ms.openlocfilehash: 8cb2609aca910056b5243fddc868710581e576e7
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480898"
---
# <a name="range-of-char-values"></a>char 值的範圍

**ANSI 3.2.1.1**"單純"**字元**的值範圍是否與**帶正負**號的字元或不**帶正負**號的字元相同

從 -128 到 127 的範圍中所有帶正負號的字元值。 從 0 到 255 的範圍中所有不帶正負號的字元值。

編譯器選項會將**char**的預設類型從**帶正負**號的字元變更為不帶正負號的**char。** [`/J`](../build/reference/j-default-char-type-is-unsigned.md)

## <a name="see-also"></a>請參閱

[長度](../c-language/characters.md)
