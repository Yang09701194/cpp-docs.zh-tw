---
title: 編譯器警告 （層級 1） C4122 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4122
dev_langs:
- C++
helpviewer_keywords:
- C4122
ms.assetid: 9a83eb0d-8708-42f7-988a-b0b6f2f646a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37f7928b1aa89eb66da95b4383084b2011387e0e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075408"
---
# <a name="compiler-warning-level-1-c4122"></a>編譯器警告 (層級 1) C4122

'function': alloc_text 僅適用使用 C 連結的函式

**alloc_text** pragma 只適用於以 **extern c**宣告的函式。 它不能搭配外部 C++ 函式使用。

忽略 pragma。