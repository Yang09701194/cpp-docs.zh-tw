---
title: IID_PPV_ARGS_Helper 函式
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 68dbd0b5b2e9d4fc04821a7e7e0193840b55e312
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077133"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper 函式

驗證指定之引數的類型衍生自 `IUnknown` 介面。

> [!IMPORTANT]
> 此範本特製化支援 WRL 基礎結構，但不適合直接從您的程式碼使用。 請改用[IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) 。

## <a name="syntax"></a>語法

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>參數

*T*<br/>
引數*pp*的類型。

*換*<br/>
雙向間接指標。

## <a name="return-value"></a>傳回值

引數*pp*轉型為指標對 a 的指標至**void**。

## <a name="remarks"></a>備註

如果範本參數*T*不是衍生自 `IUnknown`，就會產生編譯時期錯誤。

## <a name="requirements"></a>需求

**標頭：** client.h
