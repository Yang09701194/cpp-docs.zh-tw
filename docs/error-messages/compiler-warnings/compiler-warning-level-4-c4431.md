---
title: 編譯器警告 （層級 4） C4431 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4431
dev_langs:
- C++
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b44cd72548f88d922accfd571bd3ce9734b3a409
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034742"
---
# <a name="compiler-warning-level-4-c4431"></a>編譯器警告 (層級 4) C4431

遺漏類型規範 - 假設為 int。 注意: C 已不再支援 default-int

針對 Visual c + + 2005年所進行的編譯器一致性工作可能會導致此錯誤： Visual c + + 不會再預設會建立不具類型的識別項為 int。 必須明確指定識別碼的類型。

此警告預設為關閉。 如需詳細資訊，請參閱 [預設為關閉的編譯器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 。

## <a name="example"></a>範例

下列範例會產生 C4431。

```
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```