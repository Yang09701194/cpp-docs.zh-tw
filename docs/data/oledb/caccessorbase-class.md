---
title: CAccessorBase 類別
ms.date: 11/04/2016
f1_keywords:
- CAccessorBase
- CAccessorBase.Close
- CAccessorBase::Close
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
- CAccessorBase::GetNumAccessors
- GetNumAccessors
- CAccessorBase.GetNumAccessors
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
ms.openlocfilehash: 8aef8a04d7adff903e21491a91014d55aab769da
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212288"
---
# <a name="caccessorbase-class"></a>CAccessorBase 類別

OLE DB 範本中的所有存取子都是衍生自這個類別。 `CAccessorBase` 可讓一個資料列集管理多個存取子。 它也會提供參數和輸出資料行的系結。

## <a name="syntax"></a>語法

```cpp
// Replace with syntax
```

## <a name="members"></a>成員

### <a name="methods"></a>方法

|||
|-|-|
|[關閉](#close)|關閉存取子。|
|[GetHAccessor](#geth)|抓取存取子控制碼。|
|[GetNumAccessors](#getnum)|抓取類別所建立的存取子數目。|
|[IsAutoAccessor](#isauto)|測試指定的存取子是否為 autoaccessor。|
|[ReleaseAccessors](#release)|釋放存取子。|

## <a name="requirements"></a>需求

**標題:** atldbcli.h

## <a name="caccessorbaseclose"></a><a name="close"></a>CAccessorBase：： Close

關閉存取子。

### <a name="syntax"></a>語法

```cpp
void Close();
```

### <a name="remarks"></a>備註

您必須先呼叫[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md) 。

## <a name="caccessorbasegethaccessor"></a><a name="geth"></a>CAccessorBase：： GetHAccessor

擷取指定之存取子的存取子控制代碼。

### <a name="syntax"></a>語法

```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>參數

*nAccessor*<br/>
[in] 存取子的零位移數字。

### <a name="return-value"></a>傳回值

存取子控制代碼。

## <a name="caccessorbasegetnumaccessors"></a><a name="getnum"></a>CAccessorBase：： GetNumAccessors

抓取類別所建立的存取子數目。

### <a name="syntax"></a>語法

```cpp
ULONG GetNumAccessors() const;
```

### <a name="return-value"></a>傳回值

類別所建立的存取子數目。

## <a name="caccessorbaseisautoaccessor"></a><a name="isauto"></a>CAccessorBase：： IsAutoAccessor

如果在移動作業期間自動取得存取子的資料，則傳回 true。

### <a name="syntax"></a>語法

```cpp
bool IsAutoAccessor(ULONG nAccessor) const;
```

#### <a name="parameters"></a>參數

*nAccessor*<br/>
[in] 存取子的零位移數字。

### <a name="return-value"></a>傳回值

如果存取子是 autoaccessor，則傳回**true** 。 否則會傳回 **false**。

## <a name="caccessorbasereleaseaccessors"></a><a name="release"></a>CAccessorBase：： ReleaseAccessors

釋放類別所建立的存取子。

### <a name="syntax"></a>語法

```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);
```

#### <a name="parameters"></a>參數

*pUnk*<br/>
在COM 物件之 `IUnknown` 介面的指標，其已建立存取子。

### <a name="return-value"></a>傳回值

標準 HRESULT。

### <a name="remarks"></a>備註

從[CAccessorRowset：： Close](../../data/oledb/caccessorrowset-close.md)呼叫。

## <a name="see-also"></a>另請參閱

[OLE DB 消費者範本](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 消費者範本參考](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessorBase 類別](../../data/oledb/caccessorbase-class.md)
