---
title: 在 Visual Studio 中使用 Clang-整齊
description: 如何在 Microsoft C++程式碼分析的 Visual Studio 中使用 Clang-整齊。
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.openlocfilehash: 3dbe66e9d7117c027c0ec867011189824c59ce31
ms.sourcegitcommit: 21e168731b8fe0eaff18f070cee5d54aa5782c2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "77567874"
---
# <a name="using-clang-tidy-in-visual-studio"></a>在 Visual Studio 中使用 Clang-整齊

::: moniker range="<=vs-2017"

Clang 的支援需要 Visual Studio 2019 16.4 版或更新版本。 若要查看檔，請選擇檔版本選取器中的 [Visual Studio 2019]。

::: moniker-end

::: moniker range=">=vs-2019"

針對 MSBuild 和 CMake 專案，程式碼分析原本就支援[Clang](https://clang.llvm.org/extra/clang-tidy/) ，不論是使用 CLANG 或 MSVC 工具組。 Clang-整齊的檢查可作為背景程式碼分析的一部分來執行。 它們會顯示為編輯器內的警告（波浪線），並顯示在錯誤清單中。

從 Visual Studio 2019 16.4 版開始提供 Clang 支援。 當您選擇 Visual Studio 安裝程式中的C++工作負載時，它會自動包含在內。

當使用 LLVM/Clang-cl 工具組時，Clang 是預設的分析工具，MSBuild 和 CMake 都有提供。 當您使用 MSVC 工具組搭配執行或取代標準程式碼分析體驗時，可以設定它。 如果您使用 clang-cl 工具組，Microsoft 程式碼分析就無法使用。

Clang 會在編譯成功後執行。 您可能需要解決原始程式碼錯誤，才能取得 Clang 整齊的結果。

## <a name="msbuild"></a>MSBuild

您可以將 Clang 設定為同時在程式碼分析中執行，並在專案屬性視窗的 [程式**代碼分析** > **一般**] 頁面中建立。 設定工具的選項可在 [Clang-整齊] 子功能表下找到。

如需詳細資訊，請參閱[如何：設定 C/C++專案的程式碼分析屬性](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md)。

## <a name="cmake"></a>CMake

在 CMake 專案中，您可以在 `CMakeSettings.json`內設定 Clang 整齊的檢查。 開啟後，按一下 [CMake 專案設定編輯器] 右上角的 [編輯 JSON]。 辨識的金鑰如下：

- `enableMicrosoftCodeAnalysis`：啟用 Microsoft 程式碼分析
- `enableClangTidyCodeAnalysis`：啟用 Clang 整齊分析
- `clangTidyChecks`： Clang-整齊設定，以逗號分隔清單的形式指定，也就是要啟用或停用檢查

如果未指定任何 [啟用] 選項，Visual Studio 將會選取符合所使用平臺工具組的分析工具。

## <a name="warning-display"></a>警告顯示

Clang 執行會導致錯誤清單中顯示警告，並在程式碼的相關區段底下，以編輯器波浪線的形式出現。 使用 錯誤清單中的 類別 資料行來排序和組織 Clang 的警告。 您可以切換 **工具** > **選項** 底下的 停用程式碼分析波浪線 設定，以設定編輯器內的警告。

## <a name="clang-tidy-configuration"></a>Clang-整齊設定

您可以透過 [ **clang-整齊檢查**] 選項，設定在 Visual Studio 內執行 clang 的檢查。 此輸入會提供給工具的 **--檢查**引數。 任何進一步的設定都可以包含在自訂 *`.clang-tidy`* 檔案中。 如需詳細資訊，請參閱[LLVM.org 上的 Clang 檔](https://clang.llvm.org/extra/clang-tidy/)。

## <a name="see-also"></a>另請參閱

- [MSBuild 專案的 Clang/LLVM 支援](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [CMake 專案的 Clang/LLVM 支援](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
