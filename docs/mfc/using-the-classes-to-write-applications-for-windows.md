---
title: 使用類別來編寫 Windows 應用程式
ms.date: 11/04/2016
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
ms.openlocfilehash: c8b3d7061c0ef06063d9c6993f24d23fc2e1f92e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411470"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>使用類別來編寫 Windows 應用程式

綜合以上所述，Microsoft Foundation Class (MFC) 程式庫中的類別會構成的 「 應用程式架構，「 建置之 Windows 作業系統的應用程式。 在一般的層級中，架構會定義應用程式的基本架構，並提供標準的使用者介面的實作，可以置於基本架構。 您身為程式設計人員的工作是填滿其餘部分的基本架構中，這是專屬於您的應用程式的這些項目。 您可以使用 MFC 應用程式精靈建立非常徹底的入門應用程式的檔案，以取得 head start。 使用 Microsoft VisualC++資源編輯器來設計您的使用者介面項目以視覺化的方式，來連接這些項目的程式碼，並實作您的應用程式特定邏輯的類別程式庫的類別檢視 命令。

3.0 版和更新版本的 MFC 架構支援 Win32 平台，包括 Microsoft Windows 95 和更新版本的程式設計和 Windows NT 3.51 和更新版本的版本。 MFC Win32 的支援包括多執行緒處理。 使用版本 1.5*x*如果您只需要 16 位元程式設計。

此系列文章會提供應用程式架構的概觀。 它也會探討組成您的應用程式，以及如何建立這些主要物件。 這些文章中涵蓋的主題如下所示：

- [Framework](../mfc/framework-mfc.md)。

- 之間的架構和程式碼中所述[架構上建置](../mfc/building-on-the-framework.md)。

- [應用程式類別](../mfc/cwinapp-the-application-class.md)，其可封裝應用程式層級功能。

- 如何[文件範本](../mfc/document-templates-and-the-document-view-creation-process.md)建立及管理文件和其相關聯的檢視和框架視窗。

- 類別[CWnd](../mfc/window-objects.md)，所有視窗的根基底類別。

- [圖形物件](../mfc/graphic-objects.md)，例如畫筆和筆刷。

架構的其他部分包括：

- [視窗物件：概觀](../mfc/window-objects.md)

- [訊息處理和對應](../mfc/message-handling-and-mapping.md)

- [CObject，MFC 中的根基底類別](../mfc/using-cobject.md)

- [文件/檢視架構](../mfc/document-view-architecture.md)

- [對話方塊](../mfc/dialog-boxes.md)

- [控制項](../mfc/controls-mfc.md)

- [控制列](../mfc/control-bars.md)

- [OLE](../mfc/ole-in-mfc.md)

- [記憶體管理](../mfc/memory-management.md)

   除了讓您撰寫的 Windows 作業系統的應用程式的優點，MFC 也更輕鬆撰寫應用程式，特別是使用 OLE 連結和內嵌技術。 您可以讓您的應用程式 OLE 視覺化編輯容器、 OLE 視覺化編輯伺服器，或兩者，以及您可以加入自動化，讓其他應用程式可以使用從您的應用程式的物件，或甚至是從遠端磁碟。

- [MFC ActiveX 控制項](../mfc/mfc-activex-controls.md)

   OLE 控制項的開發套件 (CDK) 現在完全整合的架構。 此系列的文章提供與 MFC ActiveX 控制項開發的概觀。 （ActiveX 控制項是先前稱為 OLE 控制項。）

- [資料庫程式設計](../data/data-access-programming-mfc-atl.md)

   MFC 也提供兩組，可簡化撰寫資料存取的資料庫類別應用程式。 使用 ODBC 資料庫類別，您可以連接到資料庫，透過 「 開放式資料庫連接 (ODBC) 驅動程式、 從資料表中，選取 記錄和顯示記錄的資訊，在螢幕上的表單。 使用資料存取物件 (DAO) 類別，您可以使用資料庫透過 Microsoft Jet 資料庫引擎或外部 (非 Jet) 資料來源，包括 ODBC 資料來源。

   此外，MFC 已完全支援撰寫應用程式使用 Unicode 和多位元組字元集 (MBCS)，特別是雙位元組字元集 (DBCS)。

MFC 文件的一般指引，請參閱 <<c0> [ 一般 MFC 主題](../mfc/general-mfc-topics.md)。

## <a name="see-also"></a>另請參閱

[一般 MFC 主題](../mfc/general-mfc-topics.md)
