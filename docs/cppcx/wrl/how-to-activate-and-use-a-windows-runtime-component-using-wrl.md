---
title: 如何：利用 WRL 啟動與使用 Windows 執行階段元件
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
ms.openlocfilehash: 7f49c1362bea12576df6039b9e9f0b455cb4fae4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213950"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>如何：利用 WRL 啟動與使用 Windows 執行階段元件

本檔說明如何使用 Windows 執行階段C++範本庫（WRL）來初始化 Windows 執行階段，以及如何啟用和使用 Windows 執行階段元件。

若要使用元件，您必須取得元件所實作為類型的介面指標。 而且，由於 Windows 執行階段的基礎技術是元件物件模型（COM），因此您必須遵循 COM 規則來維護類型的實例。 例如，您必須維護*參考計數*，以決定何時從記憶體中刪除類型。

為了簡化 Windows 執行階段的使用，Windows 執行階段C++樣板程式庫會提供自動執行參考計數的智慧型指標範本（ [ComPtr\<t >](comptr-class.md)）。 當您宣告變數時，請指定 `ComPtr<`*介面名稱*`>`*識別碼*。 若要存取介面成員，請將箭號成員存取運算子（`->`）套用至識別碼。

> [!IMPORTANT]
> 當您呼叫介面函數時，請一律測試 HRESULT 傳回值。

## <a name="activating-and-using-a-windows-runtime-component"></a>啟用和使用 Windows 執行階段元件

下列步驟會使用 `Windows::Foundation::IUriRuntimeClass` 介面來示範如何建立 Windows 執行階段元件的啟動處理站、建立該元件的實例，以及取得屬性值。 它們也會示範如何初始化 Windows 執行階段。 完整的範例如下所示。

> [!IMPORTANT]
> 雖然您通常會在通用 Windows 平臺C++ （UWP）應用程式中使用 Windows 執行階段範本庫，但此範例會使用主控台應用程式來進行說明。 UWP 應用程式無法使用如 `wprintf_s` 之類的功能。 如需有關可在 UWP 應用程式中使用之類型和函式的詳細資訊，請參閱[通用 Windows 平臺應用程式中不支援的 CRT](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)函式和[適用于 uwp 應用程式的 Win32 和 COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)。

#### <a name="to-activate-and-use-a-windows-runtime-component"></a>啟用和使用 Windows 執行階段元件

1. 包含（`#include`）任何必要的 Windows 執行階段、 C++ Windows 執行階段範本程式庫C++或標準程式庫標頭。

   [!code-cpp[wrl-consume-component#2](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]

   我們建議您利用 .cpp 檔案中的 `using namespace` 指示詞，讓程式碼更容易閱讀。

2. 初始化應用程式執行所在的執行緒。 每個應用程式都必須初始化其執行緒和執行緒模型。 這個範例會使用[Microsoft：： WRL：：包裝函式：： RoInitializeWrapper](roinitializewrapper-class.md)類別來初始化 Windows 執行階段，並將[RO_INIT_MULTITHREADED](/windows/win32/api/roapi/ne-roapi-ro_init_type)指定為執行緒模型。 `RoInitializeWrapper` 類別會在結構中呼叫 `Windows::Foundation::Initialize`，並在終結時 `Windows::Foundation::Uninitialize`。

   [!code-cpp[wrl-consume-component#3](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]

   在第二個語句中， [RoInitializeWrapper：： HRESULT](roinitializewrapper-class.md#hresult)運算子會從呼叫中傳回 `Windows::Foundation::Initialize`的 `HRESULT`。

3. 建立 `ABI::Windows::Foundation::IUriRuntimeClassFactory` 介面的*啟用 factory* 。

   [!code-cpp[wrl-consume-component#4](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]

   Windows 執行階段使用完整名稱來識別類型。 `RuntimeClass_Windows_Foundation_Uri` 參數是由 Windows 執行階段提供的字串，其中包含所需的執行時間類別名稱。

4. 初始化[Microsoft：： WRL：：包裝函式：： HString](hstring-class.md)變數，其代表 `"https://www.microsoft.com"`的 URI。

   [!code-cpp[wrl-consume-component#6](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]

   在 Windows 執行階段中，您不會為 Windows 執行階段將使用的字串配置記憶體。 相反地，Windows 執行階段會在它所維護並用於作業的緩衝區中建立字串的複本，然後將控制碼傳回給它所建立的緩衝區。

5. 使用 `IUriRuntimeClassFactory::CreateUri` factory 方法來建立 `ABI::Windows::Foundation::IUriRuntimeClass` 物件。

   [!code-cpp[wrl-consume-component#7](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]

6. 呼叫 `IUriRuntimeClass::get_Domain` 方法，以取出 `Domain` 屬性的值。

   [!code-cpp[wrl-consume-component#8](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]

7. 將功能變數名稱列印到主控台並返回。 所有 `ComPtr` 和 RAII 物件都會離開範圍，並自動釋放。

   [!code-cpp[wrl-consume-component#9](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]

   [WindowsGetStringRawBuffer](/windows/win32/api/winstring/nf-winstring-windowsgetstringrawbuffer)函數會抓取 URI 字串的基礎 Unicode 格式。

以下是完整的範例：

[!code-cpp[wrl-consume-component#1](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]

## <a name="compiling-the-code"></a>編譯程式碼

若要編譯器代碼，請複製該程式碼，然後將它貼入 Visual Studio 專案中，或貼入名為 `wrl-consume-component.cpp` 的檔案中，然後在 [Visual Studio 命令提示字元] 視窗中執行下列命令。

`cl.exe wrl-consume-component.cpp runtimeobject.lib`

## <a name="see-also"></a>另請參閱

[Windows 執行階段 C++ 範本庫 (WRL)](windows-runtime-cpp-template-library-wrl.md)
