---
title: sync_shared 類別
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
ms.openlocfilehash: 029edea59f29534491232d5d99353ccb093447bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376528"
---
# <a name="sync_shared-class"></a>sync_shared 類別

描述的[同步處理篩選](../standard-library/allocators-header.md)會使用 mutex 來控制對所有配置器所共用之快取物件的存取。

## <a name="syntax"></a>語法

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>參數

|參數|描述|
|---------------|-----------------|
|*快取*|與同步處理篩選相關聯的快取類型。 這可以是 [cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md) 或 [cache_suballoc](../standard-library/cache-suballoc-class.md)。|

### <a name="member-functions"></a>成員函數

|成員函數|描述|
|-|-|
|[配置](#allocate)|配置記憶體區塊。|
|[去分配](#deallocate)|從指定位置起算的儲存體中，釋放指定數目的物件。|
|[equals](#equals)|比較兩個快取是否相等。|

## <a name="requirements"></a>需求

**標頭︰** \<allocators>

**命名空間：** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a>sync_shared:分配

配置記憶體區塊。

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>參數

|參數|描述|
|---------------|-----------------|
|*count*|所配置陣列中的元素數。|

### <a name="return-value"></a>傳回值

所配置物件的指標。

### <a name="remarks"></a>備註

成員函式會鎖定 mutex、呼叫 `cache.allocate(count)`、解除鎖定 mutex，然後傳回之前呼叫 `cache.allocate(count)` 的結果。 `cache`，代表目前的快取物件。

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a>sync_shared::d分配

從指定位置起算的儲存體中，釋放指定數目的物件。

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>參數

|參數|描述|
|---------------|-----------------|
|*Ptr*|要從儲存空間解除配置之第一個物件的指標。|
|*count*|要從儲存空間解除配置的物件數目。|

### <a name="remarks"></a>備註

此成員函式會鎖定 mutex、呼叫 `cache.deallocate(ptr, count)` (其中 `cache` 代表快取物件)，然後解除鎖定 mutex。

## <a name="sync_sharedequals"></a><a name="equals"></a>sync_shared:等於

比較兩個快取是否相等。

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>參數

|參數|描述|
|---------------|-----------------|
|*快取*|與同步處理篩選相關聯的快取類型。|
|*其他*|要比較是否相等的快取。|

### <a name="return-value"></a>傳回值

如果`cache.equals(Other.cache)``cache`的結果 表示緩存物件為**true,****則為 true;** 否則,**假**。

### <a name="remarks"></a>備註

## <a name="see-also"></a>另請參閱

[\<配置器>](../standard-library/allocators-header.md)
