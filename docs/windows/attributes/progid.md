---
title: progid (C++ COM 屬性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: d529d7362dc62207cfd72576159f560a3e04c221
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514244"
---
# <a name="progid"></a>progid

指定 COM 物件的 ProgID。

## <a name="syntax"></a>語法

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>參數

*name*<br/>
代表物件的 ProgID。

Progid 呈現了人類看得懂的類別識別碼 (CLSID) 版本, 用來識別 COM/ActiveX 物件。

## <a name="remarks"></a>備註

**Progid** C++屬性可讓您指定 COM 物件的 progid。 ProgID 的格式為*name1*。 如果您未指定 ProgID 的*版本*, 則預設版本為1。 如果您未指定*name1*, 預設名稱會是*classname. classname*。 如果您未指定**progid** , 而且您指定`vi_progid`了, 則會從`vi_progid`取得*name1* , 並附加 (下一個連續數位) 版本。

如果使用**progid**的屬性區塊不會同時使用**uuid**, 則編譯器會檢查登錄, 以查看指定之**progid**是否有**uuid**存在。 如果未指定**progid** , 則會使用版本 (如果建立 coclass, 則是 coclass 名稱) 來產生**progid**。

**progid**意指`coclass`屬性, 也就是說, 如果您指定**progid**, 則與指定`coclass`和**progid**屬性的做法相同。

**Progid**屬性會使類別以指定的名稱自動註冊。 產生的 .idl 檔案不會顯示**progid**值。

當此屬性在使用 ATL 的專案內使用時, 屬性的行為會變更。 除了上述行為之外, 此屬性所指定的資訊也會用於`GetProgID`函式中, 並`coclass`由屬性插入。 如需詳細資訊, 請參閱[coclass](coclass.md)屬性。

## <a name="example"></a>範例

如需使用**progid**的範例, 請參閱[coclass](coclass.md)的範例。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**class**、 **struct**|
|**可重複**|否|
|**必要屬性**|無|
|**無效屬性**|None|

如需有關屬性內容的詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[IDL 屬性](idl-attributes.md)<br/>
[類別屬性](class-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 屬性](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID 金鑰](/windows/win32/com/-progid--key)
