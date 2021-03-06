---
title: propput （C++ COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: 8817d0042c3055b5bbf9b111e6f02b9d9a4c152c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166441"
---
# <a name="propput"></a>propput

指定屬性設定函式。

## <a name="syntax"></a>語法

```cpp
[propput]
```

## <a name="remarks"></a>備註

**Propput** C++屬性具有與[propput](/windows/win32/Midl/propput) MIDL 屬性相同的功能。

## <a name="example"></a>範例

如需**propput**的範例用法，請參閱可系[結的範例](bindable.md)。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|方法|
|**可重複**|否|
|**必要屬性**|None|
|**無效屬性**|`propget`, `propputref`|

如需有關屬性內容的詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[IDL 屬性](idl-attributes.md)<br/>
[方法屬性](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)
