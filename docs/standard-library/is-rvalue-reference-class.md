---
title: is_rvalue_reference 類別 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b8645e9ac8a8d3e8f40590105df234b4ef55bac
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2018
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference 類別

測試類型是否為 rvalue 參考。

## <a name="syntax"></a>語法

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>參數

`Ty` 要查詢的類型。

## <a name="remarks"></a>備註

如果類型 `Ty` 是 [rvalue 參考](../cpp/rvalue-reference-declarator-amp-amp.md)，此類型述詞執行個體的值就會是 true。

## <a name="requirements"></a>需求

**標頭：**\<type_traits>

**命名空間：** std

## <a name="see-also"></a>另請參閱

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalues 和 Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
