---
title: db_table （C++ COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 2b3be55a4ea118ef3441d3ea93f63e19ebdb3d79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167247"
---
# <a name="db_table"></a>db_table

開啟 OLE DB 資料表。

## <a name="syntax"></a>語法

```cpp
[ db_table(db_table, name, source_name, hresult) ]
```

### <a name="parameters"></a>參數

*db_table*<br/>
字串，指定資料庫資料表的名稱（例如 "Products"）。

*name*<br/>
選擇性您用來處理資料表的控制碼名稱。 如果您想要傳回一個以上的結果資料列，就必須指定這個參數。 **db_table**會產生具有指定之*名稱*的變數，可用來流覽資料列集或執行多個動作查詢。

*source_name*<br/>
選擇性`db_source` 屬性（attribute）的 `CSession` 變數或實例，其會套用至命令執行所在的類別。 請參閱 [db_source](db-source.md)。

*hresult*<br/>
選擇性識別將接收此資料庫命令之 HRESULT 的變數。 如果變數不存在，則屬性會自動予以插入。

## <a name="remarks"></a>備註

**db_table**會建立[CTable](../../data/oledb/ctable-class.md)物件，供 OLE DB 取用者用來開啟資料表。 您只能在類別層級使用此屬性;您無法以內嵌方式使用它。 使用 `db_column` 將資料表資料行系結至變數;請使用 `db_param` 來分隔參數的（設定參數類型等等）。

當取用者屬性提供者將此屬性套用至類別時，編譯器會將類別重新命名為 \_*YourClassName*存取子，其中*YourClassName*是您提供給類別的名稱，而編譯器也會建立名為*YourClassName*的類別，其衍生自 \_*YourClassName*存取子。  在 [類別] 檢視中，您會看到這兩個類別。

## <a name="example"></a>範例

下列範例會開啟 Products 資料表，供 `CProducts`使用。

```cpp
// db_table.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_table(L"dbo.Products") ]
class CProducts {
   [ db_column("1") ] LONG m_ProductID;
};
```

如需應用程式中使用此屬性的範例，請參閱[MultiRead](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer)。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**class**、 **struct**|
|**可重複**|否|
|**必要屬性**|None|
|**無效屬性**|None|

如需有關屬性內容的詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[OLE DB 消費者屬性](ole-db-consumer-attributes.md)
