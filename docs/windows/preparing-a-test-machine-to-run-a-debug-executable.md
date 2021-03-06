---
title: 準備測試電腦以執行偵錯可執行檔
ms.date: 07/02/2019
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
ms.openlocfilehash: 26a92d5efc4bf9f0332a0e81fa2f9c8b2c2a958f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359914"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>準備測試電腦以執行偵錯可執行檔

若要準備電腦以測試 Visual C++ 所建置之應用程式的偵錯版本，您必須部署該應用程式所依賴之 Visual C++ 程式庫 DLL 的偵錯版本。 若要識別必須部署的 DLL，請遵循[了解 Visual C++ 應用程式的相依性](understanding-the-dependencies-of-a-visual-cpp-application.md)中的步驟。 Visual C++ 程式庫 DLL 的偵錯版本通常在名稱最後為「d」字母，例如，msvcr100.dll 的偵錯版本名稱是 msvcr100d.dll。

> [!NOTE]
> 應用程式的偵錯版本無法轉散發，而且 Visual C++ 程式庫 DLL 的偵錯版本也無法轉散發。 您只能在其他電腦上部署應用程式及 Visual C++ DLL 的偵錯版本，只為了在沒有安裝 Visual Studio 的電腦上偵錯及測試應用程式。 如需詳細資訊，請參閱[轉散發 Visual C++ 檔案](redistributing-visual-cpp-files.md)。

有三種方法可以一起部署 Visual C++ 程式庫 DLL 的偵錯版本和應用程式的偵錯版本：

- 使用包含應用程式正確的程式庫版本和架構的合併模組之安裝專案，以使用集中部署安裝特定 Visual C++ DLL 的偵錯版本至 %windir%\system32\ 目錄。 合併模組位在 \Common Files\Merge Modules\\ 的 Program Files 或 Program Files (x86) 目錄中。 合併模組的偵錯版本在名稱中有 Debug，例如 Microsoft_VC110_DebugCRT_x86.msm。 此部署的範例位於[逐步解說：使用安裝專案部署 Visual C++ 應用程式](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)。

- 使用本地部署使用 [Microsoft Visual Studio\<版本的程式檔或程式檔 (x86)\\目錄中的檔(>_VC_redist_Debug_NonRedist) 中的檔,在應用程式的安裝目錄中安裝特定 Visual C++ DLL 的調試版本。

    > [!NOTE]
    >  要在另一台電腦上使用 Visual Studio 2005 或 Visual Studio 2008 構建的應用程式進行遠端調試,必須將 C++的調試版本 C++庫 DLL 部署為共用並行程式集。 您可以使用安裝專案或 Windows Installer 安裝對應的合併模組。

- 使用 Visual Studio 的 [組態管理員]**** 對話方塊中的 [部署]**** 選項，將專案輸出和其他檔案複製至遠端電腦。

安裝 Visual C++ DLL 之後，您就可以從網路共用執行遠端偵錯工具。 如需遠端偵錯的詳細資訊，請參閱[遠端偵錯](/visualstudio/debugger/remote-debugging)。

## <a name="see-also"></a>另請參閱

[在視覺C++部署](deployment-in-visual-cpp.md)<br>
[Windows Installer 命令列選項](/windows/win32/Msi/command-line-options)<br>
[部署範例](deployment-examples.md)<br>
[遠端除錯](/visualstudio/debugger/remote-debugging)
