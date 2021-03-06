---
title: Platform::ValueType 類別
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: 889cf3a53468491517d37978ca09472756ad9b7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182947"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType 類別

實值類型執行個體的基底類別。

## <a name="syntax"></a>語法

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>公用方法

|||
|-|-|
|[ValueType::ToString](#tostring)|傳回物件的字串表示。 繼承自[platform:: object](../cppcx/platform-object-class.md)。|

### <a name="remarks"></a>備註

ValueType 類別用以建構值類型。 具有基本成員的 ValueType 衍生自物件。 不過，編譯器會中斷基本成員和衍生自 ValueType 類別之值類型的連結。 當值類型經過方塊化處理後，編譯器會重新附加這些基本成員。

### <a name="requirements"></a>需求

**最低支援用戶端：** Windows 8

**最低支援伺服器：** Windows Server 2012

**命名空間：** Platform

**中繼資料：** platform.winmd

## <a name="tostring"></a> Valuetype:: Tostring 方法

傳回物件的字串表示。

### <a name="syntax"></a>語法

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>傳回值

Platform:: string，表示的值。

## <a name="see-also"></a>另請參閱

[平台命名空間](../cppcx/platform-namespace-c-cx.md)
