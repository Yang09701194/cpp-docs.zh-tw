---
title: Make 函式
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
ms.openlocfilehash: ffd0967b741475b260eef80ec24d56874a6bcb1f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213807"
---
# <a name="make-function"></a>Make 函式

初始化指定的 Windows 執行階段類別。 使用此函式來具現化在相同模組中定義的元件。

## <a name="syntax"></a>語法

```cpp
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8,
   TArg9 &&arg9
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3
);
template <
   typename T,
   typename TArg1,
   typename TArg2
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2
);
template <
   typename T,
   typename TArg1
>
ComPtr<T> Make(
   TArg1 &&arg1
);
template <
   typename T
>
ComPtr<T> Make();
```

### <a name="parameters"></a>參數

*T*<br/>
繼承自 `WRL::RuntimeClass`的使用者指定類別。

*TArg1*<br/>
傳遞至指定執行時間類別之引數1的類型。

*TArg2*<br/>
傳遞至指定執行時間類別的引數2類型。

*TArg3*<br/>
傳遞至指定執行時間類別之引數3的類型。

*TArg4*<br/>
傳遞至指定執行時間類別之引數4的類型。

*TArg5*<br/>
傳遞至指定執行時間類別之引數5的類型。

*TArg6*<br/>
傳遞至指定執行時間類別的引數6類型。

*TArg7*<br/>
傳遞至指定執行時間類別之引數7的類型。

*TArg8*<br/>
傳遞至指定執行時間類別之引數8的類型。

*TArg9*<br/>
傳遞至指定執行時間類別之引數9的類型。

*arg1*<br/>
傳遞至指定執行時間類別的引數1。

*arg2*<br/>
傳遞至指定執行時間類別的引數2。

*arg3*<br/>
傳遞至指定執行時間類別的引數3。

*arg4*<br/>
傳遞至指定執行時間類別的引數4。

*arg5*<br/>
傳遞至指定執行時間類別的引數5。

*arg6*<br/>
傳遞至指定執行時間類別的引數6。

*arg7*<br/>
傳遞至指定執行時間類別的引數7。

*arg8*<br/>
傳遞至指定執行時間類別的引數8。

*arg9*<br/>
傳遞至指定執行時間類別的引數9。

## <a name="return-value"></a>傳回值

如果成功，則為 `ComPtr<T>` 物件;否則，`nullptr`。

## <a name="remarks"></a>備註

如需範例，請參閱[如何：直接具現化 WRL 元件](how-to-instantiate-wrl-components-directly.md)，以瞭解此函式和[MICROSOFT：： WRL：:D Etails：： MakeAndInitialize](makeandinitialize-function.md)之間的差異。

## <a name="requirements"></a>需求

**標頭：** implements。h

**命名空間：** Microsoft::WRL

## <a name="see-also"></a>另請參閱

[Microsoft::WRL 命名空間](microsoft-wrl-namespace.md)
