---
title: is_bind_expression 類別
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_bind_expression
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
ms.openlocfilehash: 6cd6d45788ec36f6827d1403ce3f7e5057004433
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245202"
---
# <a name="isbindexpression-class"></a>is_bind_expression 類別

測試類型是否是透過呼叫 `bind` 來產生的。

## <a name="syntax"></a>語法

```
template<class Ty>
struct is_bind_expression {
   static const bool value;
};
```

## <a name="remarks"></a>備註

如果類型 `Ty` 是對 `bind` 的呼叫所傳回的類型，常數成員 `value` 便為 true，否則為 false。

## <a name="example"></a>範例

```cpp
// std__functional__is_bind_expression.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}
```

```Output
0
1
```
