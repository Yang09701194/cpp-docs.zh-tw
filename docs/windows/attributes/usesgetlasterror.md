---
title: usesgetlasterror （C++ COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: f58929db01a1710e811a973c0559ad29b242b4eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166129"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

告訴呼叫者，如果在呼叫該函式時發生錯誤，則呼叫端可以呼叫 `GetLastError` 來取得錯誤碼。

## <a name="syntax"></a>語法

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>備註

**Usesgetlasterror** C++屬性具有與[usesgetlasterror](/windows/win32/Midl/usesgetlasterror) MIDL 屬性相同的功能。

## <a name="example"></a>範例

如需如何使用**usesgetlasterror**的範例，請參閱[idl_module](idl-module.md)範例。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**module**屬性|
|**可重複**|否|
|**必要屬性**|None|
|**無效屬性**|None|

如需有關屬性內容的詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[IDL 屬性](idl-attributes.md)
