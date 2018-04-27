---
title: is_class 類別 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_class
dev_langs:
- C++
helpviewer_keywords:
- is_class class
- is_class
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 62657a6037dfe2eb9c676411dae7d444fe9dbe17
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2018
---
# <a name="isclass-class"></a>is_class 類別

測試類型是否為類別。

## <a name="syntax"></a>語法

```cpp
template <class Ty>
struct is_class;
```

### <a name="parameters"></a>參數

`Ty` 要查詢的類型。

## <a name="remarks"></a>備註

如果類型 `Ty` 是定義為 `class` 或 `struct` 的類型，或定義為上述其中一個的 `cv-qualified` 表單，則類型述詞的執行個體為 true。

## <a name="example"></a>範例

```cpp
// std__type_traits__is_class.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_class<trivial> == " << std::boolalpha
        << std::is_class<trivial>::value << std::endl;
    std::cout << "is_class<int> == " << std::boolalpha
        << std::is_class<int>::value << std::endl;

    return (0);
    }

```

```Output
is_class<trivial> == true
is_class<int> == false
```

## <a name="requirements"></a>需求

**標頭：**\<type_traits>

**命名空間：** std

## <a name="see-also"></a>另請參閱

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_compound 類別](../standard-library/is-compound-class.md)<br/>
[is_union 類別](../standard-library/is-union-class.md)<br/>
