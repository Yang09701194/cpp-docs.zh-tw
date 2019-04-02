---
title: ModuleType 列舉
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
ms.openlocfilehash: 937649eada481f7c45359fa0816266f62dc03875
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784584"
---
# <a name="moduletype-enumeration"></a>ModuleType 列舉

指定模組是否應支援同處理序伺服程式或跨處理序伺服程式。

## <a name="syntax"></a>語法

```cpp
enum ModuleType;
```

## <a name="members"></a>成員

### <a name="values"></a>值

|名稱|描述|
|----------|-----------------|
|`InProc`|同處理序伺服器。|
|`OutOfProc`|跨處理序伺服器。|
|`DisableCaching`|停用在模組上的快取機制。|
|`InProcDisableCaching`|組合`InProc`和`DisableCaching`。|
|`OutOfProcDisableCaching`|組合`OutOfProc`和`DisableCaching`。|

## <a name="requirements"></a>需求

**標頭：** module.h

**命名空間：** Microsoft:: wrl

## <a name="see-also"></a>另請參閱

[Microsoft::WRL 命名空間](microsoft-wrl-namespace.md)