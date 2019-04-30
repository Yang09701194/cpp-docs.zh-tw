---
title: 編譯器警告 (層級 2) C4309
ms.date: 11/04/2016
f1_keywords:
- C4309
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
ms.openlocfilehash: 41184571dc07213c796c039170966a0c7150bd45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402472"
---
# <a name="compiler-warning-level-2-c4309"></a>編譯器警告 (層級 2) C4309

'conversion': 常數值遭截斷

類型轉換會導致超過配置給它的空間的常數。 您可能需要使用較大的類型常數。

下列範例會產生 C4309:

```
// C4309.cpp
// compile with: /W2
int main()
{
   char c = 128;   // C4309
}
```