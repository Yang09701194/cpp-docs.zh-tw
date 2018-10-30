---
title: 執行緒 （c + + COM 屬性） |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85ffa775fd18b6979fccf4354ce243f017634d02
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059671"
---
# <a name="threading-c"></a>threading (C++)

指定 COM 物件的執行緒模型。

## <a name="syntax"></a>語法

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>參數

*model*<br/>
（選擇性）其中一個下列的執行緒模型：

- `apartment` （apartment 執行緒）

- `neutral` （沒有使用者介面的.NET framework 元件）

- `single` （簡單執行緒）

- `free` （無限制執行緒）

- `both` （apartment 和無限制執行緒）

預設值是 `apartment`。

## <a name="remarks"></a>備註

**執行緒**c + + 屬性未出現在所產生的.idl 檔案，但將您的 COM 物件的實作中使用。

在 ATL 專案中，如果[coclass](coclass.md)屬性也會出現，所指定的執行緒模型*模型*傳遞做為範本參數[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)類別插入`coclass`屬性。

**執行緒**屬性也能存取[event_source](event-source.md)。

## <a name="example"></a>範例

請參閱[授權](licensed.md)的範例使用的範例**執行緒**。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**類別**，**結構**|
|**可重複**|否|
|**必要屬性**|**coclass**|
|**無效屬性**|無|

如需有關屬性內容的詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[COM 屬性](com-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 屬性](typedef-enum-union-and-struct-attributes.md)<br/>
[類別屬性](class-attributes.md)<br/>
[舊版程式碼的多執行緒支援 (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[中性 Apartment](/windows/desktop/cossdk/neutral-apartments)