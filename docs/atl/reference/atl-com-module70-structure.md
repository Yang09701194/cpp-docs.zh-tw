---
title: _ATL_COM_MODULE70 結構
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: c6361fc5374ed732cd9ccbfbbd1d3d1c2fc8f1f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261280"
---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70 結構

ATL 中的 COM 相關程式碼使用

## <a name="syntax"></a>語法

```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```

## <a name="members"></a>成員

`cbSize`<br/>
結構，用來進行版本設定的大小。

`m_hInstTypeLib`<br/>
型別程式庫，此模組控制代碼的執行個體。

`m_ppAutoObjMapFirst`<br/>
指出此模組的物件對應項目開頭的陣列元素的位址。

`m_ppAutoObjMapLast`<br/>
指出物件的對應項目，此模組結束陣列元素的位址。

`m_csObjMap`<br/>
將序列化物件的對應項目存取的重要區段。 供內部使用 ATL

## <a name="remarks"></a>備註

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)定義為 _ATL_COM_MODULE70 的 typedef。

## <a name="requirements"></a>需求

**標頭：** atlbase.h

## <a name="see-also"></a>另請參閱

[類別和結構](../../atl/reference/atl-classes.md)
