---
title: 圖形物件
ms.date: 11/04/2016
f1_keywords:
- HRGN
- HFONT
- HBITMAP
helpviewer_keywords:
- CRgn class [MFC], HRGN handle type
- HPEN [MFC]
- objects [MFC], graphic
- palettes [MFC], creating in device context
- pens [MFC], creating in device context
- bitmaps [MFC], creating in device contexts
- palette objects [MFC]
- memory [MFC], display contexts
- MFC, graphic objects
- regions [MFC], creating in device context
- CPen class [MFC], HPEN handle type
- GDI objects [MFC]
- HRGN [MFC]
- graphic objects [MFC]
- GDI objects [MFC], graphic-object classes
- CFont class [MFC], HFONT handle type
- HFONT and class CFont [MFC]
- HBITMAP and class CBitmap [MFC]
- fonts [MFC], creating in device context
- images [MFC], graphic objects [MFC]
- CBitmap class [MFC], HBITMAP handle type
- HPALETTE and class CPalette [MFC]
- CBrush class [MFC], HBRUSH handle type
- objects [MFC], graphic objects
- drawing [MFC], in device contexts
- device contexts [MFC], graphic objects [MFC]
- brushes [MFC], creating in device context
- region objects [MFC]
- pen objects [MFC]
- GDI [MFC], graphic-object classes
- graphic objects [MFC], creating in device context
- HBRUSH and class CBrush [MFC]
- painting and device context [MFC]
- CPalette class [MFC], HPALETTE handle type
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
ms.openlocfilehash: 0201e53114b71c02877762f89cc65fc46d17700c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370518"
---
# <a name="graphic-objects"></a>圖形物件

Windows 在裝置內容中提供各式各樣的可用繪圖工具。 它提供可繪製線條的畫筆、可填滿內部的筆刷和可繪製文字的字型。 MFC 提供相當於 Windows 中繪圖工具的圖形物件類別。 下表顯示可用的類別和對等的 Windows 繪圖裝置介面 (GDI) 控制代碼類型。

> [!NOTE]
> 有關詳細資訊,請參閱[GDI+ SDK 文件](/windows/win32/gdiplus/-gdiplus-gdi-start)。

這篇文章說明如何使用這些圖形物件類別：

### <a name="classes-for-windows-gdi-objects"></a>Windows GDI 物件的類別

|類別|Windows 控制代碼類型|
|-----------|-------------------------|
|[CPen](../mfc/reference/cpen-class.md)|`HPEN`|
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|

> [!NOTE]
> 類[CImage](../atl-mfc-shared/reference/cimage-class.md)提供了增強的位圖支援。

類別庫中的每個圖形物件類別都有一個建構函式，可讓您建立該類別的圖形物件，接著您必須使用適當的建立函式來初始化，例如 `CreatePen`。

類別庫中的每個圖形物件類別都具有一個轉型運算子，可將MFC 物件轉型成相關聯的 Windows 控制代碼。 除非相關聯的物件與產生的控制代碼中斷連結，否則產生的控制代碼無效。 使用對`Detach`象的成員函數分離句柄。

下列程式碼會將 `CPen` 物件轉型成 Windows 控制代碼：

[!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]

#### <a name="to-create-a-graphic-object-in-a-device-context"></a>在裝置內容中建立圖形物件

1. 在堆疊框架上定義圖形物件。 使用類型特有的建立函式來初始化物件，例如 `CreatePen`。 此外，初始化建構函式中的物件。 請參閱有關[單階段和兩階段創建](../mfc/one-stage-and-two-stage-construction-of-objects.md)的討論,該討論提供示例代碼。

1. [將物件選擇到當前設備上下文中](../mfc/selecting-a-graphic-object-into-a-device-context.md),保存之前選擇的舊圖形物件。

1. 完成目前的圖形物件時，選取將舊圖形物件放回裝置內容中，以便還原其狀態。

1. 允許在結束範圍時，自動刪除框架配置的圖形物件。

> [!NOTE]
> 如果您將重複使用某個圖形物件，您可以配置它一次，並在每次需要時，選擇將該物件放入裝置內容中。 當您不再需要時，請務必刪除這類物件。

### <a name="what-do-you-want-to-know-more-about"></a>你想知道更多

- [圖形物件的一階段和兩階段建構](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [以一階段和兩階段建構畫筆的範例](../mfc/one-stage-and-two-stage-construction-of-objects.md)

- [選取圖形物件放入裝置內容中](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [裝置內容](../mfc/device-contexts.md)

## <a name="see-also"></a>另請參閱

[視窗物件](../mfc/window-objects.md)
