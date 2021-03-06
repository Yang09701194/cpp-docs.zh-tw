---
title: ActiveX 控制項容器：在非對話方塊容器中使用控制項
ms.date: 11/04/2016
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
ms.openlocfilehash: 70a67a6952d5361177b89e3ba514d7036b5799b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394867"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX 控制項容器：在非對話方塊容器中使用控制項

在某些應用程式 (例如 SDI 或 MDI 應用程式) 中，您會想要在應用程式的視窗中內嵌控制項。 **Create**成員函式，包裝函式類別，插入的視覺效果的C++，可以不需要 對話方塊中，以動態方式建立控制項的執行個體。

**建立**成員函式具有下列參數：

*lpszWindowName*<br/>
要在控制項的 Text 或 Caption 屬性 (如果有的話) 中顯示的文字指標。

*dwStyle*<br/>
視窗樣式。 如需完整清單，請參閱 < [cwnd:: Createcontrol](../mfc/reference/cwnd-class.md#createcontrol)。

*rect*<br/>
指定控制項的大小和位置。

*pParentWnd*<br/>
指定控制項的父視窗，通常是 `CDialog`。 不能**NULL**。

*nID*<br/>
指定控制項 ID，而且可以由容器使用以參考控制項。

使用此函式動態建立 ActiveX 控制項的範例會在 SDI 應用程式的表單檢視中。 您接著可以在應用程式的 `WM_CREATE` 處理常式中建立控制項的執行個體。

對於這個範例中，`CMyView` 是主要檢視類別，而 `CCirc` 是包裝函式類別，CIRC.H 則是包裝函式類別的標頭 (.H) 檔案。

實作此功能需要四個步驟。

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>若要在非對話方塊視窗中動態建立 ActiveX 控制項

1. 只要在 `CMyView` 類別定義之前，於 CMYVIEW.H 中插入 CIRC.H：

   [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. 將成員變數 (為 `CCirc` 類型) 新增至位於 CMYVIEW.H 的 `CMyView` 類別定義的受保護區段：

   [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. 將 `WM_CREATE` 訊息處理常式新增至類別 `CMyView`。

1. 在處理常式函式`CMyView::OnCreate`，呼叫以控制項的`Create`函式使用**這**與父視窗的指標：

   [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. 重建專案。 每當應用程式檢視建立時，Circ 控制項就會動態建立。

## <a name="see-also"></a>另請參閱

[ActiveX 控制項容器](../mfc/activex-control-containers.md)
