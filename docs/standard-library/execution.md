---
title: '&lt;執行&gt;'
ms.date: 04/18/2019
f1_keywords:
- <execution>
- std::<execution>
helpviewer_keywords:
- execution header
ms.openlocfilehash: 81e9aa63265c367412fda709aacd5ca3953e9fdf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445038"
---
# <a name="ltexecutiongt"></a>&lt;執行&gt;

描述平行演算法的執行原則。

## <a name="syntax"></a>語法

```
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```

### <a name="classes-and-structs"></a>類別和結構

|||
|-|-|
|[is_execution_policy 結構](is-execution-policy-struct.md)|針對排除函式簽章的目的，偵測執行原則，否則不明確的多載解析參與。|
|[parallel_policy 類別](parallel-policy-class.md)|用來做為唯一的類型，以區分平行演算法多載，並指出平行演算法的執行可能會平行處理。|
|[parallel_unsequenced_policy 類別](parallel-unsequenced-policy-class.md)|用來做為唯一的類型來區分平行演算法多載，並指出平行演算法的執行可能會平行處理和向量化。|
|[sequenced_policy 類別](sequenced-policy-class.md)|用來做為唯一的類型來區分平行演算法多載，並要求平行演算法的執行可能不會平行處理。|

## <a name="requirements"></a>需求

**標頭：** \<執行 >

**命名空間：** stdext

## <a name="see-also"></a>另請參閱

[標頭檔參考資料](cpp-standard-library-header-files.md)\
[C++ 標準程式庫中的執行緒安全](thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準程式庫參考資料](cpp-standard-library-reference.md)
