---
title: 使用書籤
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 5a4a2d65ba7367b5568603b5f08a07c6d85cc4a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209309"
---
# <a name="using-bookmarks"></a>使用書籤

在開啟資料列集之前，您必須告知提供者您想要使用書簽。 若要這麼做，請在您的屬性集內，將 `DBPROP_BOOKMARKS` 屬性設定為**true** 。 提供者會將書簽抓取為數據行零，因此，如果您使用靜態存取子，則必須使用特殊宏 BOOKMARK_ENTRY 和 `CBookmark` 類別。 `CBookmark` 是範本類別，其中引數是書簽緩衝區的長度（以位元組為單位）。 書簽所需的緩衝區長度取決於提供者。 如果您使用的是 ODBC OLE DB 提供者（如下列範例所示），則緩衝區必須是4個位元組。

```cpp
class CProducts
{
public:
   CBookmark<4> bookmark;

   BEGIN_COLUMN_MAP(CProducts)
      BOOKMARK_ENTRY(bookmark)
   END_COLUMN_MAP()
};
```

然後，使用下列程式碼：

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

如果您使用 `CDynamicAccessor`，則會在執行時間以動態方式設定緩衝區。 在此情況下，您可以使用未指定緩衝區長度之 `CBookmark` 的特製化版本。 使用函數 `GetBookmark` 從目前的記錄抓取書簽，如下列程式碼範例所示：

```cpp
CTable<CDynamicAccessor> product;
CBookmark<> bookmark;
CDBPropSet propset(DBPROPSET_ROWSET);
CSession session;

propset.AddProperty(DBPROP_BOOKMARKS, true);
product.Open(session, "Products", &propset);
product.MoveNext();
product.GetBookmark(&bookmark);
```

如需在提供者中支援書簽的詳細資訊，請參閱[提供者支援書簽](../../data/oledb/provider-support-for-bookmarks.md)。

## <a name="see-also"></a>另請參閱

[使用存取子](../../data/oledb/using-accessors.md)
