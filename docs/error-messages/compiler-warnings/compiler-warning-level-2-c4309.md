---
title: 編譯器警告 （層級 2） C4309 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4309
dev_langs:
- C++
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b7eba833b547a54adc0644303ab51d3852740a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041970"
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