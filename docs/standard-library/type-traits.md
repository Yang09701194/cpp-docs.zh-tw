---
title: '&lt;type_traits&gt;'
ms.date: 02/21/2019
f1_keywords:
- <type_traits>
helpviewer_keywords:
- typetrait header
- type_traits
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
ms.openlocfilehash: a0d7f57d13b4387dd5ba39048adf65d9ec7ca3f5
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2019
ms.locfileid: "72684417"
---
# <a name="lttype_traitsgt"></a>&lt;type_traits&gt;

定義編譯時間常數的範本，這些常數會提供其類型引數之屬性的相關資訊，或產生轉換的類型。

## <a name="syntax"></a>語法

```cpp
#include <type_traits>
```

## <a name="remarks"></a>備註

@No__t_0type_traits > 中的類別和範本是用來在編譯時期支援型別推斷、分類和轉換。 它們也可用來偵測與類型相關的錯誤，並協助您優化您的一般程式碼。 一元型別特性描述型別的屬性，二進位型別特性描述型別之間的關聯性，而轉換特性則會修改類型的屬性。

Helper 類別 `integral_constant` 及其樣板特製化 `true_type` 而且 `false_type` 會形成型別述詞的基類。 「類型述詞」是採用一或兩個類型引數的範本。 當類型述詞*為 true*時，它會直接或間接從[true_type](../standard-library/type-traits-typedefs.md#true_type)公開衍生。 當類型述詞*保留 false*時，它會直接或間接從[false_type](../standard-library/type-traits-typedefs.md#false_type)公開衍生。

*類型修飾詞*或*轉換特性*是採用一或多個範本引數的範本，且具有一個成員 `type`，這是已修改類型的同義字。

### <a name="alias-templates"></a>別名範本

為了簡化型別特性運算式，會提供 `typename some_trait<T>::type` 的[別名範本](../cpp/aliases-and-typedefs-cpp.md)，其中*some_trait*是類別樣板名稱。 例如，[add_const](../standard-library/add-const-class.md) 具有其類型 `add_const_t` 的別名範本，定義為：

```cpp
template <class T>
using add_const_t = typename add_const<T>::type;
```

這些是為 `type` 成員提供的別名：

||||
|-|-|-|
| add_const_t | add_cv_t | add_lvalue_reference_t |
| add_pointer_t | add_rvalue_reference_t | add_volatile_t |
| aligned_storage_t | aligned_union_t | common_type_t |
| conditional_t | decay_t | enable_if_t |
| invoke_result_t | make_signed_t | make_unsigned_t |
| remove_all_extents_t | remove_const_t | remove_cv_t |
| remove_extent_t | remove_pointer_t | remove_reference_t |
| remove_volatile_t | result_of_t | underlying_type_t |

### <a name="classes"></a>類別

Helper 類別和 typedef

|||
|-|-|
|[integral_constant](../standard-library/integral-constant-class-bool-constant-class.md)|從類型及值建立整數常數。|
|[true_type](../standard-library/type-traits-typedefs.md#true_type)|存有具有 True 值的整數常數。|
|[false_type](../standard-library/type-traits-typedefs.md#false_type)|存有具有 False 值的整數常數。|

主要的類型類別

|||
|-|-|
|[is_void](../standard-library/is-void-class.md)|測試類型是否為**void**。|
|[is_null_pointer](../standard-library/is-null-pointer-class.md)|測試類型是否為 `std::nullptr_t`。|
|[is_integral](../standard-library/is-integral-class.md)|測試類型是否為整數。|
|[is_floating_point](../standard-library/is-floating-point-class.md)|測試類型是否為浮點。|
|[is_array](../standard-library/is-array-class.md)|測試類型是否為陣列。|
|[is_pointer](../standard-library/is-pointer-class.md)|測試類型是否為指標。|
|[is_lvalue_reference](../standard-library/is-lvalue-reference-class.md)|測試類型是否為 lvalue 參考。|
|[is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)|測試類型是否為 rvalue 參考。|
|[is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)|測試類型是否為成員物件的指標。|
|[is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)|測試類型是否為成員函式的指標。|
|[is_enum](../standard-library/is-enum-class.md)|測試類型是否為列舉。|
|[is_union](../standard-library/is-union-class.md)|測試類型是否為等位。|
|[is_class](../standard-library/is-class-class.md)|測試類型是否為類別。|
|[is_function](../standard-library/is-function-class.md)|測試類型是否為函式類型。|

複合類型類別

|||
|-|-|
|[is_reference](../standard-library/is-reference-class.md)|測試類型是否為參考。|
|[is_arithmetic](../standard-library/is-arithmetic-class.md)|測試類型是否為算術。|
|[is_fundamental](../standard-library/is-fundamental-class.md)|測試類型是否為**void**或算術。|
|[is_object](../standard-library/is-object-class.md)|測試類型是否為物件類型。|
|[is_scalar](../standard-library/is-scalar-class.md)|測試類型是否為純量。|
|[is_compound](../standard-library/is-compound-class.md)|測試類型是否不是純量。|
|[is_member_pointer](../standard-library/is-member-pointer-class.md)|測試類型是否為成員的指標。|

類型屬性

|||
|-|-|
|[is_const](../standard-library/is-const-class.md)|測試類型是否為**const**。|
|[is_volatile](../standard-library/is-volatile-class.md)|測試類型是否為**volatile**。|
|[is_trivial](../standard-library/is-trivial-class.md)|測試類型是否為 trivial。|
|[is_trivially_copyable](../standard-library/is-trivially-copyable-class.md)|測試類型是否可完整複製。|
|[is_standard_layout](../standard-library/is-standard-layout-class.md)|測試類型是否為標準配置類型。|
|[is_pod](../standard-library/is-pod-class.md)|測試類型是否為 POD。|
|[is_literal_type](../standard-library/is-literal-type-class.md)|測試類型是否可以是 `constexpr` 變數或用於 `constexpr` 函式。|
|[is_empty](../standard-library/is-empty-class.md)|測試類型是否為空的類別。|
|[is_polymorphic](../standard-library/is-polymorphic-class.md)|測試類型是否為多型類別。|
|[is_abstract](../standard-library/is-abstract-class.md)|測試類型是否有抽象類別。|
|[is_final](../standard-library/is-final-class.md)|測試類型是否為標示 `final` 的類別類型。|
|[is_aggregate](../standard-library/is-aggregate-class.md)||
|[is_signed](../standard-library/is-signed-class.md)|測試類型是否為有正負號整數。|
|[is_unsigned](../standard-library/is-unsigned-class.md)|測試類型是否為無正負號整數。|
|[is_constructible](../standard-library/is-constructible-class.md)|測試類型是否可使用指定的引數類型建構。|
|[is_default_constructible](../standard-library/type-traits-functions.md#is_default_constructible)|測試類型是否有預設建構函式。|
|[is_copy_constructible](../standard-library/type-traits-functions.md#is_copy_constructible)|測試類型是否有複製建構函式。|
|[is_move_constructible](../standard-library/type-traits-functions.md#is_move_constructible)|測試類型是否有移動建構函式。|
|[is_assignable](../standard-library/type-traits-functions.md#is_assignable)|測試第一個類型是否可以指派第二個類型的值。|
|[is_copy_assignable](../standard-library/type-traits-functions.md#is_copy_assignable)|測試類型是否可指派類型的常數參考值。|
|[is_move_assignable](../standard-library/type-traits-functions.md#is_move_assignable)|測試類型是否可指派類型的右值參考。|
|[is_swappable](../standard-library/type-traits-functions.md#is_swappable)||
|[is_swappable_with](../standard-library/type-traits-functions.md#is_swappable_with)||
|[is_destructible](../standard-library/is-destructible-class.md)|測試類型是否為易損壞的。|
|[is_trivially_constructible](../standard-library/is-trivially-constructible-class.md)|測試類型在使用指定的類型建構時是否不使用任何非 trivial 作業。|
|[is_trivially_default_constructible](../standard-library/is-trivially-default-constructible-class.md)|測試類型在預設建構時是否不使用任何非 trivial 作業。|
|[is_trivially_copy_constructible](../standard-library/is-trivially-copy-constructible-class.md)|測試類型在複製建構時是否不使用任何非 trivial 作業。|
|[is_trivially_move_constructible](../standard-library/type-traits-functions.md#is_trivially_move_constructible)|測試類型在移動建構時是否不使用任何非 trivial 作業。|
|[is_trivially_assignable](../standard-library/is-trivially-assignable-class.md)|測試類型是否可指派，且指派不使用任何非 trivial 作業。|
|[is_trivially_copy_assignable](../standard-library/type-traits-functions.md#is_trivially_copy_assignable)|測試類型是否可指派複製，且指派不使用任何非 trivial 作業。|
|[is_trivially_move_assignable](../standard-library/type-traits-functions.md#is_trivially_move_assignable)|測試類型是否可指派移動，且指派不使用任何非 trivial 作業。|
|[is_trivially_destructible](../standard-library/is-trivially-destructible-class.md)|測試類型是否可破壞，且解構函式不使用任何非 trivial 作業。|
|[is_nothrow_constructible](../standard-library/is-nothrow-constructible-class.md)|測試類型是否可建構，且已知在使用指定的類型建構時不會擲回。|
|[is_nothrow_default_constructible](../standard-library/is-nothrow-default-constructible-class.md)|測試類型是否可預設建構，且已知在預設建構時不會擲回。|
|[is_nothrow_copy_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|測試類型是否可複製建構，且已知複製建構函式不會擲回。|
|[is_nothrow_move_constructible](../standard-library/is-nothrow-move-constructible-class.md)|測試類型是否可移動建構，且已知移動建構函式不會擲回。|
|[is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)|測試類型是否可使用指定類型指派，且已知指派不會擲回。|
|[is_nothrow_copy_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|測試類型是否可指派複製，且已知指派不會擲回。|
|[is_nothrow_move_assignable](../standard-library/type-traits-functions.md#is_nothrow_move_assignable)|測試類型是否可指派移動，且已知指派不會擲回。|
|[is_nothrow_swappable](../standard-library/type-traits-functions.md#is_nothrow_swappable)||
|[is_nothrow_swappable_with](../standard-library/type-traits-functions.md#is_nothrow_swappable_with)||
|[is_nothrow_destructible](../standard-library/is-nothrow-destructible-class.md)|測試類型是否可破壞，且已知解構函式不會擲回。|
|`has_virtual_destructor`|測試類型是否有虛擬解構函式。|
|`has_unique_object_representations`||
| [is_invocable](is-invocable-classes.md) | 測試是否可以使用指定的引數類型叫用可呼叫的類型。<br/> 已在 c + + 17 中新增。 |
| [is_invocable_r](is-invocable-classes.md) | 測試是否可以使用指定的引數類型叫用可呼叫的類型，並將結果轉換成指定的類型。<br/> 已在 c + + 17 中新增。 |
| [is_nothrow_invocable](is-invocable-classes.md) | 測試是否可以使用指定的引數類型叫用可呼叫的類型，而且已知不會擲回例外狀況。<br/> 已在 c + + 17 中新增。 |
| [is_nothrow_invocable_r](is-invocable-classes.md) | 測試是否可以使用指定的引數類型叫用可呼叫型別，而且已知不會擲回例外狀況，而且結果會轉換成指定的型別。<br/> 已在 c + + 17 中新增。 |

類型屬性的查詢

|||
|-|-|
|[alignment_of](../standard-library/alignment-of-class.md)|取得類型的對齊方式。|
|[rank](../standard-library/rank-class.md)|取得陣列維度的數目。|
|[extent](../standard-library/extent-class.md)|取得指定陣列維度中的項目數目。|

類型關聯

|||
|-|-|
|[is_same](../standard-library/is-same-class.md)|測試兩個類型是否一樣。|
|[is_base_of](../standard-library/is-base-of-class.md)|測試某個類型是否為另一個類型的基底。|
|[is_convertible](../standard-library/is-convertible-class.md)|測試某個類型是否可轉換為另一個類型。|

常數 volatile 修改

|||
|-|-|
|[add_const](../standard-library/add-const-class.md)|從類型產生**const**類型。|
|[add_volatile](../standard-library/add-volatile-class.md)|從類型產生**volatile**類型。|
|[add_cv](../standard-library/add-cv-class.md)|從類型產生**const volatile**類型。|
|[remove_const](../standard-library/remove-const-class.md)|從類型產生非常數類型。|
|[remove_volatile](../standard-library/remove-volatile-class.md)|從類型產生非 volatile 類型。|
|[remove_cv](../standard-library/remove-cv-class.md)|從類型產生非常數非 volatile 類型。|

參考修改

|||
|-|-|
|[add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)|從類型產生類型的參考。|
|[add_rvalue_reference](../standard-library/add-rvalue-reference-class.md)|從類型產生類型的右值參考|
|[remove_reference](../standard-library/remove-reference-class.md)|從類型產生非參考類型。|

簽章修改

|||
|-|-|
|[make_signed](../standard-library/make-signed-class.md)|如果已簽章或者最小已簽章類型的大小大於或等於類型，則產生類型。|
|[make_unsigned](../standard-library/make-unsigned-class.md)|如果未簽章或者最小未簽章類型的大小大於或等於類型，則產生類型。|

陣列修改

|||
|-|-|
|[remove_all_extents](../standard-library/remove-all-extents-class.md)|從陣列類型產生非陣列類型。|
|[remove_extent](../standard-library/remove-extent-class.md)|從陣列類型產生項目類型。|

指標修改

|||
|-|-|
|[add_pointer](../standard-library/add-pointer-class.md)|從類型產生類型的指標。|
|[remove_pointer](../standard-library/remove-pointer-class.md)|從類型的指標產生類型。|

其他轉換

|||
|-|-|
|[aligned_storage](../standard-library/aligned-storage-class.md)|為對齊類型配置未初始化的記憶體。|
|[aligned_union](../standard-library/aligned-union-class.md)|使用非簡單式建構函式或解構函式為對齊的聯集配置未初始化的記憶體。|
|[common_type](../standard-library/common-type-class.md)|產生參數封裝之所有類型的一般類型。|
|[conditional](../standard-library/conditional-class.md)|如果條件為 true，則產生第一個指定的類型，反之則產生第二個指定的類型。|
|[decay](../standard-library/decay-class.md)|由值來傳遞時，會產生類型。 建立非參考、非常數或非暫時性的類型，或建立類型的指標。|
|[enable_if](../standard-library/enable-if-class.md)|如果條件為 true，則產生指定的類型，反之則不產生類型。|
|[invoke_result](invoke-result-class.md)|決定採用指定引數類型之可呼叫類型的傳回類型。 <br/>已在 c + + 17 中新增。 |
|[result_of](../standard-library/result-of-class.md)|決定採用指定引數類型之可呼叫類型的傳回類型。 <br/>已在 c + + 14 中新增，在 c + + 17 中被取代 |
|[underlying_type](../standard-library/underlying-type-class.md)|產生列舉類型的基礎整數類型。|

邏輯運算子特性

|||
|-|-|
|[聯手](../standard-library/conjunction-class.md)||
|[分離](../standard-library/disjunction-class.md)||
|[取](../standard-library/negation-class.md)||

## <a name="see-also"></a>請參閱

[\<functional>](../standard-library/functional.md)
