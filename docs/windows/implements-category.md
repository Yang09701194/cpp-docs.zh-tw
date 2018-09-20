---
title: implements_category |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.implements_category
dev_langs:
- C++
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e329f179a2a9c61fc3be6d351dc8baa97c1d4c6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377148"
---
# <a name="implementscategory"></a>implements_category

指定目標類別所實作的元件類別。

## <a name="syntax"></a>語法

```cpp
[ implements_category(
   implements_category="uuid"
) ]
```

### <a name="parameters"></a>參數

*implements_category*<br/>
實作的類別目錄的識別碼。

## <a name="remarks"></a>備註

**Implements_category** c + + 屬性會指定目標類別所實作的元件類別。 這是藉由建立類別目錄的對應，並加入所指定的個別項目**implements_category**屬性。 如需詳細資訊，請參閱 <<c0> [ 元件類別和執行它們的運作方式為何？](https://msdn.microsoft.com/library/windows/desktop/ms694322)。

此屬性需要 [coclass](../windows/coclass.md)、 [progid](../windows/progid.md)或 [vi_progid](../windows/vi-progid.md) 屬性 (或表示上述其中一項的另一個屬性) 也套用至相同的項目。 如果使用任何單一屬性，則會自動套用其他兩項。 例如，如果`progid`會套用`vi_progid`和`coclass`也會套用。

## <a name="example"></a>範例

下列程式碼可讓您指定下列物件會實作`Control`類別目錄。

```cpp
// cpp_attr_ref_implements_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLib")];
[ coclass, implements_category("CATID_Control"),
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]
class CMyClass {};
```

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**類別**，**結構**|
|**可重複**|是|
|**必要屬性**|下列其中之一： `coclass`， `progid`，或 `vi_progid`|
|**無效屬性**|無|

如需詳細資訊，請參閱 [屬性內容](../windows/attribute-contexts.md)。

## <a name="see-also"></a>另請參閱

[COM 屬性](../windows/com-attributes.md)<br/>
[類別屬性](../windows/class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)  