---
title: 編譯器警告 C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: 6164fd2e19e35233ba67feb84d117f1e4e01f20d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311043"
---
# <a name="compiler-warning-c4694"></a>編譯器警告 C4694

> '*類別*': 密封抽象類別不能有基底類別'*base_class*'

抽象和密封類別無法從參考類型繼承，密封和抽象類別無法實作基底類別函式，也不允許自己用作為基底類別。

如需詳細資訊，請參閱 <<c0> [ 抽象](../../extensions/abstract-cpp-component-extensions.md)，[密封](../../extensions/sealed-cpp-component-extensions.md)，並[類別和結構](../../extensions/classes-and-structs-cpp-component-extensions.md)。

這個警告會自動升級為錯誤。 如果您想要修改此行為，使用[#pragma 警告](../../preprocessor/warning.md)。

## <a name="example"></a>範例

下列範例會產生 C4694。

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```