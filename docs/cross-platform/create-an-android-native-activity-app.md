---
title: 建立 Android Native Activity 應用程式
ms.date: 10/17/2019
ms.assetid: 884014b1-5208-45ec-b0da-ad0070d2c24d
ms.openlocfilehash: f588c56acfd5c559e6b0bf1b8635e8b36c69548a
ms.sourcegitcommit: a673f6a54cc97e3d4cd032b10aa8dce7f0539d39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "78177445"
---
# <a name="create-an-android-native-activity-app"></a>建立 Android Native Activity 應用程式

當您安裝具有工作負載的跨平臺行動裝置開發時，Visual Studio 可以用來建立功能完整**的C++**  Android Native Activity 應用程式。 Android 原生開發套件 (NDK) 是一個可讓您實作大部分完全使用 C/C++ 程式碼之 Android 應用程式的工具集。 一些 Java JNI 程式碼可做為讓 C/C++ 程式碼與 Android 互動的黏著劑。 Android NDK 引進了使用 Android 應用程式開發介面層級 9 建立 Native Activity 應用程式的功能。 Native Activity 程式碼在建立使用 Unreal 引擎或 OpenGL 的遊戲和圖形密集應用程式方面很受歡迎。 本主題會引導您建立使用 OpenGL 的簡易 Native Activity 應用程式。 其他主題會引導您逐步了解開發人員編輯、建置、偵錯和部署 Native Activity 程式碼的週期。

## <a name="requirements"></a>需求

建立 Android Native Activity 應用程式之前，您必須確定您已符合所有系統需求，並已**使用C++**  Visual Studio 中的工作負載來安裝行動裝置開發。 如需詳細資訊，請參閱[使用C++安裝跨平臺行動開發](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)。 請確定安裝中包含必要的協力廠商工具和 Sdk，而且已安裝 Android 模擬器。

## <a name="create-a-new-native-activity-project"></a>建立新的 Native Activity 專案

在本教學課程中，您會先建立新的 Android Native Activity 專案，然後在 Android 模擬器中建立並執行預設應用程式。

::: moniker range="vs-2017"

1. 在 Visual Studio 中，**選擇 [** 檔案 >**新增**>**專案**]。

1. 在 [**新增專案**] 對話方塊的 [**範本**] 底下，選擇 [  **C++ Visual** >**跨平臺**]，然後選擇 [**原生活動應用程式（Android）** ] 範本。

1. 提供應用程式的名稱，例如*myandroidapp.packaging*，然後選擇 **[確定]** 。

   ![建立原生活動專案](../cross-platform/media/cppmdd-newproject.png "建立 Native Activity 專案")

   Visual Studio 會建立新的方案，並開啟方案總管。

   ![方案總管中的原生活動專案](../cross-platform/media/cppmdd-rc-na-solutionexp.png "方案總管中的 Native Activity 專案")

::: moniker-end

::: moniker range=">=vs-2019"

1. 在 Visual Studio 中，**選擇 [** 檔案 >**新增**>**專案**]。

1. 在 [**建立新專案**] 對話方塊中，選取 [**原生活動應用程式（Android）** ] 範本，然後選擇 [**下一步]** 。

1. 在 [**設定您的新專案**] 對話方塊中，于 [**專案名稱**] 中輸入*myandroidapp.packaging*之類的名稱，然後選擇 [**建立**]。

   Visual Studio 會建立新的方案，並開啟方案總管。

::: moniker-end

新的 Android Native Activity 應用程式方案包含兩個專案：

- `MyAndroidApp.NativeActivity` 包含參考和黏附程式碼 (glue code)，可讓您的應用程式當做 Native Activity 在 Android 上執行。 黏合程式碼 (glue code) 的進入點實作位於 *main.cpp* 中。 先行編譯標頭檔位於 *pch.h* 中。 這個 Native Activity 應用程式專案會編譯至封裝專案所挑選的共用程式庫 *.so* 檔案中。

- `MyAndroidApp.Packaging` 會建立部署在 Android 裝置或模擬器上時所使用的 *.apk* 檔案。 其中包含資源以及您設有資訊清單屬性的 *AndroidManifest.xml* 檔案。 其中也包含用來控制建置流程的 *build.xml* 檔案。 根據預設，它會設定為啟始專案，以便直接從 Visual Studio 部署及執行。

## <a name="build-and-run-the-default-android-native-activity-app"></a>建置並執行預設 Android Native Activity 應用程式

建置並執行範本所產生的應用程式，以驗證您的安裝和設定。 針對此初始測試，請在 Android 模擬器所安裝的其中一個裝置設定檔上執行應用程式。 如果您想要在其他目標上測試您的應用程式，您可以載入目標模擬器，或將裝置連接至您的電腦。

## <a name="to-build-and-run-the-default-native-activity-app"></a>建置並執行預設 Native Activity 應用程式

1. 若尚未選取，請從 [方案平台] 下拉式清單中選擇 [x86] 。

     ![方案平臺下拉式 x86 選擇](../cross-platform/media/cppmdd-rc-na-solution-x86.png "方案平台下拉式 x86 選取範圍")

     如果未顯示 [方案平台] 清單，請從 [新增或移除按鈕] 下拉式清單中選擇 [x86]，然後選擇您的平台。

1. 在功能表列上選擇 [建置] > [建置解決方案]。

     [輸出] 視窗會顯示方案中這兩個專案的建置流程輸出。

1. 選擇其中一個 Android 模擬器設定檔作為部署目標。

     如果您已經安裝其他模擬器或連接 Android 裝置，就可以在部署目標下拉式清單中加以選擇。

1. 按**f5**開始進行調試，或按**Shift**+**F5**啟動而不進行調試。

   以下是預設應用程式在 Android 模擬器中看起來的樣子。

   ![執行您應用程式的模擬器](../cross-platform/media/cppmdd-emulator-running-app.png "執行您應用程式的模擬器")

   Visual Studio 啟動模擬器，這需要幾秒的時間來載入及部署您的程式碼。 在您的應用程式啟動之後，您可以設定中斷點，並使用偵錯工具，以逐步執行程式碼、檢查本機及監看值。

1. 按 **Shift**+**F5** 停止偵錯。

   模擬器是分開的程序，會繼續執行。 您可以將程式碼多次編輯、編譯及部署至相同的模擬器。
