---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: 73de3c2d19063f0738b8b0a3c510ea520f58de0b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745053"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**Microsoft 特定的**

調用封裝**Release**介面指標`IUnknown`上的釋放成員函數。

## <a name="syntax"></a>語法

```cpp
void Release( );
```

## <a name="remarks"></a>備註

呼叫`IUnknown::Release`封裝的介面指標,如果此介面指標`E_POINTER`為 NULL,則引發錯誤。

**結束微軟的**

## <a name="see-also"></a>另請參閱

[_com_ptr_t類](../cpp/com-ptr-t-class.md)
