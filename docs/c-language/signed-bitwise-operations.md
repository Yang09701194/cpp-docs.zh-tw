---
title: 帶正負號的位元運算
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: 43f65fd5d1ea14ef5e15f18d9c8516ccf5fb1e08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158315"
---
# <a name="signed-bitwise-operations"></a>帶正負號的位元運算

**ANSI 3.3**：帶正負號整數位元運算的結果

帶正負號整數的位元運算運作方式，與不帶正負號整數的位元運算相同。 例如，`-16 & 99` 可以用二進位運算式表示為

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

位元 AND 的結果為 96。

## <a name="see-also"></a>請參閱

[整數](../c-language/integers.md)
