---
title: ClickOnce Deployment for Visual C++ Applications
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: 4726fda8c5eca70ce7acde19f141a7c096395e95
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316615"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>ClickOnce Deployment for Visual C++ Applications

Visual Studio 提供部署 Windows 應用程式的兩種不同技術：ClickOnce 部署或 [Windows Installer](/windows/win32/Msi/windows-installer-portal) 部署。

## <a name="clickonce-deployment-in-c"></a>C++ 中的 ClickOnce 部署

Visual C++開發環境並不直接支援使用 ClickOnce 部署 Visual Studio C++專案,但可以使用這些工具。

> [!NOTE]
> Visual Studio 在 Visual C# 和 Visual Basic 開發環境中支援 ClickOnce。 如果 Visual Studio C++專案是 Visual C++ 專案的依賴項,則可以使用從 Visual C# 開發環境進行 ClickOnce 部署來發佈應用程式(包括其依賴項)。

若要使用 ClickOnce 部署 Visual c + + 應用程式，您必須先使用 [Mage.exe (資訊清單產生和編輯工具)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) 或它的圖形化使用者介面版本 (如需資訊，請參閱[MageUI.exe (資訊清單產生和編輯工具、圖形化用戶端)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client))，建置 [ClickOnce 應用程式資訊清單](/visualstudio/deployment/clickonce-application-manifest)和 [ClickOnce 部署資訊清單](/visualstudio/deployment/clickonce-deployment-manifest)。

請先使用 Mage.exe 建置應用程式資訊清單，產生的檔案會有 .manifest 的副檔名。 接著，使用 Mage.exe 建置部署資訊清單，而產生的檔案會有 .application 的副檔名。 然後，簽名資訊清單。

應用程式資訊清單必須指定目標處理器 (**x86**、**x64** 或 **ARM**)。 請參閱 [64 位元應用程式的部署必要條件](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications)，以取得這些選項的詳細資訊。

此外，應用程式和部署資訊清單的名稱必須與 C++ 應用程式的名稱不同。 這可避免 Mage.exe 所建立的應用程式資訊清單，與屬於 C++ 應用程式一部分的外部資訊清單發生衝突。

您的部署將需要安裝應用程式所依賴的任何 Visual C++ 程式庫。 若要判斷特定應用程式的相依性，您可以搭配 /DEPENDENTS 選項使用 depends.exe 或 DUMPBIN 公用程式。 如需相依性的詳細資訊，請參閱[了解 Visual C++ 應用程式的相依性](understanding-the-dependencies-of-a-visual-cpp-application.md)。 您可能必須執行 VCRedist.exe，這個公用程式會在目標電腦中安裝 Visual C++ 程式庫。

此外，您可能還需要為應用程式建置啟動載入器 (Bootstrapper) (必要條件安裝程式) 來部署必要條件元件。如需啟動載入器的詳細資訊，請參閱[建立啟動載入器套件](/visualstudio/deployment/creating-bootstrapper-packages)。

如需這項技術的詳細描述，請參閱 [ClickOnce 安全性和部署](/visualstudio/deployment/clickonce-security-and-deployment)。 如需 ClickOnce 部署的詳細範例，請參閱[逐步解說：以手動方式部署 ClickOnce 應用程式](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)。

## <a name="see-also"></a>另請參閱

[Mage.exe(清單產生和編輯工具)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe(清單產生和編輯工具,圖形用戶端)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[Makecert.exe (憑證建立工具)](/windows/win32/SecCrypto/makecert)<br>
[部署桌面應用程式](deploying-native-desktop-applications-visual-cpp.md)<br>
[部署應用程式、服務和元件](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[單擊"一次安全和部署"](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[建立啟動載入器套件](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[.NET 程式設計,帶C++/CLI(視覺C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[本機與 .NET 互通性](../dotnet/native-and-dotnet-interoperability.md)
