---
title: 轉散發 MFC 程式庫
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
ms.openlocfilehash: e1434bee6d134d4c02b2c06125d340a68a6c305d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359908"
---
# <a name="redistributing-the-mfc-library"></a>轉散發 MFC 程式庫

如果您以動態方式將應用程式連結至 MFC 程式庫，則必須轉散發相應的 MFC DLL。 例如，如果 MFC 應用程式是使用 Visual Studio 2015 所隨附的 MFC 版本所建置，您必須轉散發 mfc140.dll 或 mfc140u.dll，視您的應用程式是針對窄字元或 Unicode 支援進行編譯而定。

> [!NOTE]
> Visual Studio 2015 RTM 的可轉散發檔案目錄中已省略 mfc140.dll 檔案。 您可以改為使用 Windows\system32 和 Windows\syswow64 目錄中 Visual Studio 2015 所安裝的版本。

因為所有的 MFC DLL 會使用 C 執行階段程式庫 (CRT) 的共用版本，您可能也需要轉散發 CRT。 Visual Studio 2015 所隨附的 MFC 版本會使用通用 CRT 程式庫，該程式庫是作為 Windows 10 的一部分散發。 若要執行使用 Visual Studio 2015 在舊版 Windows 上建置的 MFC 應用程式，您必須轉散發通用 CRT。 如需如何轉散發通用 CRT 作為作業系統元件或使用本機部署轉散發通用 CRT 的資訊，請參閱 [Introducing the Universal CRT](https://devblogs.microsoft.com/cppblog/introducing-the-universal-crt/) (通用 CRT 簡介)。 要下載通用 CRT 以在受支援的 Windows 版本上進行集中部署,請參閱[Windows 10 通用 C 執行時](https://www.microsoft.com/download/details.aspx?id=48234)。 Windows SDK 中提供用於本機部署的 ucrtbase.dll 可轉散發架構特定版本。 根據預設，Visual Studio 會將這些版本安裝在 C:\Program Files (x86)\Windows Kits\10\Redist\ucrt\DLLs\ 的架構特定子目錄中。

如果應用程式是使用舊版 MFC 程式庫所建置，您必須從可轉散發檔案目錄中轉散發相應的 CRT DLL。 例如，如果 MFC 應用程式是使用 Visual Studio 2013 (vc120) 工具組所建置，您必須轉散發 msvcr120.dll。 您也需要轉散發相應的 mfc`<version>`u.dll 或 mfc`<version>`.dll。

如果您以靜態方式將應用程式連結至 MFC (亦即，如果在 [屬性頁]**** 對話方塊的 [一般]**** 索引標籤上指定 [在靜態程式庫中使用 MFC]****)，您不需要轉散發 MFC DLL。 不過，雖然靜態連結可能適用於應用程式的測試和內部部署，但還是建議您不要使用它來轉散發 MFC。 如需部署 Visual C++ 程式庫之建議策略的詳細資訊，請參閱[選擇部署方法](choosing-a-deployment-method.md)。

如果應用程式會使用實作 WebBrowser 控制項的 MFC 類別 (例如，[類別](../mfc/reference/chtmlview-class.md)或 [CHtmlEditView 類別](../mfc/reference/chtmleditview-class.md))，建議您同時安裝最新版本的 Microsoft Internet Explorer，讓目標電腦具有最新的通用控制項檔案。 (至少需要 Internet 資源管理器 4.0。有關如何安裝 Internet Explorer 元件的資訊,請造訪 Microsoft 支援網站上的「第 185375 條:如何創建 Internet 資源管理器的單 EXE 安裝」。。

如果應用程式會使用 MFC 資料庫類別 (例如，[CRecordset 類別](../mfc/reference/crecordset-class.md)和 [CRecordView 類別](../mfc/reference/crecordview-class.md))，您必須轉散發 ODBC 和應用程式所使用的任何 ODBC 驅動程式。

如果 MFC 應用程式使用 Windows Forms 控制項，您必須隨著應用程式轉散發 mfcmifc80.dll。 這個 DLL 是使用強式名稱簽署的 .NET 組件，可隨著其應用程式本機資料夾中的應用程式轉散發，或使用 [Gacutil.exe (全域組件快取工具)](/dotnet/framework/tools/gacutil-exe-gac-tool) 將其部署到全域組件快取 (GAC) 中來轉散發。

如果您轉散發 MFC DLL，請確定轉散發的是零售版，而不是偵錯版本。 DLL 的偵錯版本不是可轉散發檔案。 MFC DLL 的偵錯版本名稱以 "d" 結尾，例如 Mfc140d.dll。

您可以使用 VCRedist_*architecture*.exe、使用隨 Visual Studio 一起安裝的合併模組，或在應用程式所在的相同資料夾中部署 MFC DLL，藉此轉散發 MFC。 如需如何轉散發 MFC 的詳細資訊，請參閱[轉散發 Visual C++ 檔案](redistributing-visual-cpp-files.md)。

## <a name="installation-of-localized-mfc-components"></a>安裝當地語系化的 MFC 元件

如果您決定要安裝 MFC 當地語系化 DLL 將應用程式當地語系化，您必須使用可轉散發合併檔案 (.msm)。 比方說，如果您想要在 x86 電腦上將應用程式當地語系化，您必須將 Microsoft_VC`<version>`_MFCLOC_x86.msm 合併到 x86 電腦的安裝套件中。

可轉散發的 .msm 檔案包含可用於當地語系化的 DLL。 每種支援的語言都有一個 DLL。 安裝處理序會將這些 DLL 安裝在目標電腦的 %windir%\system32\ 資料夾中。

如需如何當地語系化 MFC 應用程式的詳細資訊，請參閱 [TN057：MFC 元件的當地語系化](../mfc/tn057-localization-of-mfc-components.md)。

您可以藉由部署應用程式本機資料夾中的 MFC DLL，來轉散發 MFC 當地語系化 DLL。 如需如何轉散發 Visual C++ 程式庫的詳細資訊，請參閱[轉散發 Visual C++ 檔案](redistributing-visual-cpp-files.md)。

## <a name="see-also"></a>另請參閱

[轉散發 Visual C++ 檔案](redistributing-visual-cpp-files.md)
