---
title: 標準命令
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
ms.openlocfilehash: 987023322e38584d10901c1ab1fe20ac46926bd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307155"
---
# <a name="standard-commands"></a>標準命令

架構定義許多標準命令訊息。 這些命令的 ID 通常會採用下列格式：

**ID_** *來源*_*項目*

何處*來源*通常是功能表名稱並*項目*是功能表項目。 例如，在 [檔案] 功能表上的新命令的命令 ID 是 ID_FILE_NEW。 標準命令 ID 在文件中以粗體顯示。 程式設計人員定義的 ID 會以與周圍文字不同的字型顯示。

下列是受支援之某些最重要的命令的清單：

*檔案功能表命令*<br/>
新增、開啟、關閉、儲存、另存新檔、版面設定、列印設定、列印、預覽列印、匯出和最近使用的檔案。

*編輯功能表命令*<br/>
清除、全部清除、複製、剪下、尋找、貼上、重複、取代、全選、移除和重做。

*檢視功能表命令*<br/>
工具列和狀態列。

*視窗功能表命令*<br/>
新增、安排、重疊顯示、水平並排、垂直並排和分割。

*說明功能表命令*<br/>
索引、使用說明和關於。

*OLE 命令 （[編輯] 功能表）*<br/>
插入新物件、 編輯連結、 貼上連結、 選擇性貼上並*typename*物件 （動詞命令）。

此架構會為這些命令提供各種支援層級。 某些命令的支援僅限於定義的命令 ID，而其他的支援則為徹底的實作。 例如，此架構會藉由建立新文件物件、顯示 [開啟] 對話方塊以及開啟和讀取檔案，以實作 [檔案] 功能表上的 [開啟] 命令。 相反地，您必須實作命令在 [編輯] 功能表上自行，因為等 ID_EDIT_COPY 命令取決於資料性質，所以您要複製。

如需支援的命令的詳細資訊和提供實作的層級，請參閱[技術提示 22](../mfc/tn022-standard-commands-implementation.md)。 標準命令定義於檔案 AFXRES.H 中。

## <a name="see-also"></a>另請參閱

[使用者介面物件和命令識別碼](../mfc/user-interface-objects-and-command-ids.md)
