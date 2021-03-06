---
title: ActiveX 控制項容器
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
ms.openlocfilehash: e8340acafc81447052fcb8d90df8997e81dc4117
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394854"
---
# <a name="activex-control-containers"></a>ActiveX 控制項容器

ActiveX 控制項容器是一種完全支援 ActiveX 控制項的容器，可以將其合併至自己的視窗或對話方塊中。 ActiveX 控制項可讓您在許多開發專案中重複使用的軟體項目。 控制項可讓您應用程式的使用者存取資料庫、監視資料，以及在您的應用程式中做出各種選擇。 如需有關 ActiveX 控制項的詳細資訊，請參閱文章[MFC ActiveX 控制項](../mfc/mfc-activex-controls.md)。

>[!IMPORTANT]
> ActiveX 是舊版的技術，不應用於新的開發。 如需詳細資訊，請參閱 < [ActiveX 控制項](activex-controls.md)。

控制項容器在專案中通常會有兩種形式：

- 對話方塊和類似對話方塊的視窗 (例如表單檢視)，其中 ActiveX 控制項會用於對話方塊中的某個位置。

- 應用程式中的視窗，其中 ActiveX 控制項用於工具列，或使用者視窗中的其他位置。

ActiveX 控制項容器進行互動的控制項，透過公開[方法](../mfc/mfc-activex-controls-methods.md)並[屬性](../mfc/mfc-activex-controls-properties.md)。 這些方法和屬性可以透過控制項容器存取和修改，您可以透過 ActiveX 控制項容器專案中的包裝函式類別進行存取。 內嵌的 ActiveX 控制項也可以與容器互動所引發 （傳送）[事件](../mfc/mfc-activex-controls-events.md)通知動作已經發生的容器。 控制項容器可以選擇是否要針對這些通知採取行動。

其他文章中討論的幾個主題，從建立 ActiveX 控制項容器專案到與使用 Visual C++ 建置之 ActiveX 控制項容器相關的基礎實作問題：

- [建立 MFC ActiveX 控制項容器](../mfc/reference/creating-an-mfc-activex-control-container.md)

- [ActiveX 控制項的容器](../mfc/containers-for-activex-controls.md)

- [ActiveX 控制項容器：手動啟用 ActiveX 控制項內含項目](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)

- [ActiveX 控制項容器：將控制項插入控制項容器應用程式中](../mfc/inserting-a-control-into-a-control-container-application.md)

- [ActiveX 控制項容器：將 ActiveX 控制項連接至成員變數](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)

- [ActiveX 控制項容器：處理事件從 ActiveX 控制項](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)

- [ActiveX 控制項容器：檢視及修改控制項屬性](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)

- [ActiveX 控制項容器：在 ActiveX 控制項容器中程式設計 ActiveX 控制項](../mfc/programming-activex-controls-in-a-activex-control-container.md)

- [ActiveX 控制項容器：在非對話方塊容器中使用控制項](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)

如需使用 ActiveX 控制項在對話方塊中的詳細資訊，請參閱[對話方塊編輯器](../windows/dialog-editor.md)主題。

取得一份文章，其說明的詳細資料的開發 ActiveX 控制項使用視覺效果C++和 MFC ActiveX 控制項類別，請參閱[MFC ActiveX 控制項](../mfc/mfc-activex-controls.md)。 這些文章會依功能分類為不同群組。

## <a name="see-also"></a>另請參閱

[MFC ActiveX 控制項](../mfc/mfc-activex-controls.md)
