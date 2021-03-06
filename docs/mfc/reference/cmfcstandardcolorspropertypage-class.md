---
title: CMFCStandardColorsPropertyPage 類別
ms.date: 11/04/2016
helpviewer_keywords:
- CMFCStandardColorsPropertyPage class [MFC]
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
ms.openlocfilehash: 91cfa609c31e83c02cce8b2a474a9b66ec3ba56f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388627"
---
# <a name="cmfcstandardcolorspropertypage-class"></a>CMFCStandardColorsPropertyPage 類別

表示屬性頁使用者用來在 [色彩] 對話方塊中選取標準色彩。

## <a name="syntax"></a>語法

```
class CMFCStandardColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>成員

### <a name="public-constructors"></a>公用建構函式

|||
|-|-|
|名稱|描述|
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|預設建構函式。|

### <a name="public-methods"></a>公用方法

|||
|-|-|
|名稱|描述|
|`CMFCStandardColorsPropertyPage::CreateObject`|由建立此類別類型的動態執行個體架構所使用。|
|`CMFCStandardColorsPropertyPage::GetThisClass`|Framework 用來取得的指標[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)與此類別類型相關聯的物件。|

### <a name="remarks"></a>備註

`CMFCColorDialog`類別會使用這個類別顯示標準色彩屬性頁。 如需詳細資訊`CMFCColorDialog`，請參閱 < [CMFCColorDialog 類別](../../mfc/reference/cmfccolordialog-class.md)。

## <a name="inheritance-hierarchy"></a>繼承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

## <a name="requirements"></a>需求

**標頭：** afxstandardcolorspropertypage.h

## <a name="see-also"></a>另請參閱

[階層架構圖表](../../mfc/hierarchy-chart.md)<br/>
[類別](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog 類別](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCCustomColorsPropertyPage 類別](../../mfc/reference/cmfccustomcolorspropertypage-class.md)
