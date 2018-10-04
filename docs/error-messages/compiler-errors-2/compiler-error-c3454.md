---
title: 編譯器錯誤 C3454 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3454
dev_langs:
- C++
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e469f6715775288720c61ad8a61e16956e4c63d1
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789159"
---
# <a name="compiler-error-c3454"></a>編譯器錯誤 C3454

類別宣告上不允許 [attribute]

必須定義類別，它才能是屬性。

如需詳細資訊，請參閱 <<c0> [ 屬性](../../windows/attributes/attribute.md)。

## <a name="example"></a>範例

下列範例會產生 C3454。

```
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```