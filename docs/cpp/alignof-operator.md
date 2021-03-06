---
title: __alignof 運算子
ms.date: 12/17/2018
f1_keywords:
- __alignof_cpp
- alignof_cpp
- __alignof
- _alignof
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
ms.openlocfilehash: 6bddce29dd97d965303a58cc72aa97dfe8cbd8d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181534"
---
# <a name="__alignof-operator"></a>__alignof 運算子

C + + 11 引進的**alignof**運算子會傳回指定類型的對齊（以位元組為單位）。 若要獲得最高可攜性，您應該使用 alignof 運算子，而不是 Microsoft-specific __alignof 運算子。

**Microsoft 專屬**

傳回類型的值，`size_t` 這是類型的對齊需求。

## <a name="syntax"></a>語法

```cpp
  __alignof( type )
```

## <a name="remarks"></a>備註

例如：

|運算是|值|
|----------------|-----------|
|**__alignof （char）**|1|
|**__alignof （短）**|2|
|**__alignof （int）**|4|
|**__alignof （\__int64）**|8|
|**__alignof （float）**|4|
|**__alignof （雙精度浮點數）**|8|
|**__alignof （char\*）**|4|

**__Alignof**值與基本類型 `sizeof` 的值相同。 不過，請考慮這個範例：

```cpp
typedef struct { int a; double b; } S;
// __alignof(S) == 8
```

在此情況下， **__alignof**值是結構中最大元素的對齊需求。

同樣地，針對

```cpp
typedef __declspec(align(32)) struct { int a; } S;
```

`__alignof(S)` 等於 `32`。

**__Alignof**的一種用法就是您的其中一個記憶體配置常式的參數。 例如，假設有下列定義的結構 `S`，您可以呼叫名為 `aligned_malloc` 的記憶體配置常式，至特定對齊界限上配置記憶體。

```cpp
typedef __declspec(align(32)) struct { int a; double b; } S;
int n = 50; // array size
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));
```

為了與舊版相容，除非指定了編譯器選項[/za \(停用語言擴充功能）](../build/reference/za-ze-disable-language-extensions.md) ，否則 **_alignof**是 **__alignof**的同義字。

如需修改對齊的詳細資訊，請參閱：

- [pack](../preprocessor/pack.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [/Zp (結構成員對齊)](../build/reference/zp-struct-member-alignment.md)

- [結構對齊範例](../build/x64-software-conventions.md#examples-of-structure-alignment)（x64 專用）

如需適用於 x86 和 x64 之程式碼中的對齊差異的詳細資訊，請參閱：

- [與 x86 編譯器衝突](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)

**END Microsoft 特定的**

## <a name="see-also"></a>另請參閱

[具有一元運算子的運算式](../cpp/expressions-with-unary-operators.md)<br/>
[關鍵字](../cpp/keywords-cpp.md)
