---
title: swap 函式 (auto_handle)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- swap function
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
ms.openlocfilehash: 9e6cde103eefb6e14fdf2a3fc7e3299070afbc25
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446869"
---
# <a name="swap-function-auto_handle"></a>swap 函式 (auto_handle)

在一個 `auto_handle` 和另一個之間交換物件。

## <a name="syntax"></a>語法

```
template<typename _element_type>
void swap(
   auto_handle<_element_type> % _left,
   auto_handle<_element_type> % _right
);
```

#### <a name="parameters"></a>參數

*_left*<br/>
`auto_handle`。

*_right*<br/>
另一個 `auto_handle`。

## <a name="example"></a>範例

```cpp
// msl_swap_auto_handle.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1 = "string one";
   auto_handle<String> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   swap( s1, s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>需求

**標頭檔**\<msclr \ auto_handle. h >

**命名空間**msclr

## <a name="see-also"></a>另請參閱

[auto_handle](../dotnet/auto-handle.md)<br/>
[auto_handle::swap](../dotnet/auto-handle-swap.md)
