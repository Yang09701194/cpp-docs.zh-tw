---
title: MFC 如何讓您更輕鬆地建立網際網路用戶端應用程式
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
ms.openlocfilehash: ffeed3a844fb86acf1bf8c5181c59529824c27f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405751"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC 如何讓您更輕鬆地建立網際網路用戶端應用程式

Microsoft Foundation Classes 會封裝 Win32 Internet Extension (WinInet) 函式，並且提供 MFC 程式設計人員熟悉的內容。 MFC 提供三種網際網路檔案類別 ([CInternetFile](../mfc/reference/cinternetfile-class.md)， [CHttpFile](../mfc/reference/chttpfile-class.md)，並[CGopherFile](../mfc/reference/cgopherfile-class.md)) 衍生自[CStdioFile](../mfc/reference/cstdiofile-class.md)類別. 這些類別除了讓 `CStdioFile` 用於本機檔案的程式設計人員熟悉擷取與操作網際網路資料外，您還可以使用這些類別以一致、透明的方式處理本機檔案和網際網路檔案。

MFC WinInet 類別針對跨網際網路傳輸的資料提供與 `CStdioFile` 相同的功能。 這些類別會將 HTTP、FTP 和 Gopher 的網際網路通訊協定擷取至高階應用程式開發介面，提供快速而直接路徑，使應用程式具有網際網路功能。 例如，在低層級連線到 FTP 伺服器仍然需要許多個步驟，而身為 MFC 開發人員，您只需要呼叫 `CInternetSession::GetFTPConnection` 即可建立該連線。

此外，MFC WinInet 類別可提供下列優點：

- 緩衝的 I/O

- 資料的類型安全控制代碼

- 諸多函式的預設參數

- 常見網際網路錯誤的例外狀況處理

- 自動清除開啟的控制代碼和連線

## <a name="see-also"></a>另請參閱

[Win32 網際網路延伸模組 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[WinInet 如何讓您更輕鬆地建立網際網路用戶端應用程式](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)
