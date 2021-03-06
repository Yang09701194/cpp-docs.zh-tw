---
title: MIDL 編譯器屬性頁
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 57498a01-fccc-4a0e-a036-6ff702f83126
f1_keywords:
- VC.Project.VCMidlTool.PreprocessorDefinitions
- VC.Project.VCMidlTool.AdditionalIncludeDirectories
- VC.Project.VCMidlTool.AdditionalMetadataDirectories
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.MkTypLibCompatible
- VC.Project.VCMidlTool.WarningLevel
- VC.Project.VCMidlTool.WarnAsError
- VC.Project.VCMidlTool.SuppressStartupBanner
- VC.Project.VCMidlTool.DefaultCharType
- VC.Project.VCMidlTool.TargetEnvironment
- VC.Project.VCMidlTool.GenerateStublessProxies
- VC.Project.VCMidlTool.SuppressCompilerWarnings
- VC.Project.VCMidlTool.ApplicationConfigurationMode
- VC.Project.VCMidlTool.LocaleID
- VC.Project.VCMidlTool.MultiProcMIDL
- VC.Project.VCMidlTool.OutputDirectory
- VC.Project.VCMidlTool.WinmdFileName
- VC.Project.VCMidlTool.HeaderFileName
- VC.Project.VCMidlTool.DLLDataFileName
- VC.Project.VCMidlTool.InterfaceIdentifierFileName
- VC.Project.VCMidlTool.ProxyFileName
- VC.Project.VCMidlTool.GenerateTypeLibrary
- VC.Project.VCMidlTool.TypeLibraryName
- VC.Project.VCMidlTool.GenerateClientFiles
- VC.Project.VCMidlTool.GenerateServerFiles
- VC.Project.VCMidlTool.ClientStubFile
- VC.Project.VCMidlTool.ServerStubFile
- VC.Project.VCMidlTool.TypeLibFormat
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.PreendWithABINamepsace
- VC.Project.VCMidlTool.ValidateParameters
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.MinimumTargetSystem
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d6833230baca892836c187799df7f0658aa16772
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336245"
---
# <a name="midl-property-pages"></a>MIDL 屬性頁

MIDL 屬性頁作為 項屬性在上可用。使用 COM 的 C++專案中的 IDL 檔。 使用它們來設定[MIDL 編譯器](/windows/win32/midl/using-the-midl-compiler-2)。 如需如何以程式設計方式存取 C++ 專案的 MIDL 選項的資訊，請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> 物件。 另請參閱[一般 MIDL 命令列語法](/windows/win32/midl/general-midl-command-line-syntax)。

## <a name="general-property-page"></a>一般屬性頁

### <a name="preprocessor-definitions"></a>前置處理器定義

指定或多個定義,包括 MIDL 巨集 (\][/D)](/windows/win32/midl/-d)\[巨集 。

### <a name="additional-include-directories"></a>其他 Include 目錄

指定要添加到包含路徑[(/I](/windows/win32/midl/-i)\[路徑\]) 的一個或多個目錄。

### <a name="additional-metadata-directories"></a>其他中繼資料目錄

指定包含 Windows.Foundation.WinMD 檔的目錄[(/metadata_dir](/windows/win32/midl/-metadata-dir)\[路徑\])。

### <a name="enable-windows-runtime"></a>開啟 Windows 執行時

啟用 Windows 執行時語義以創建 Windows 中數據檔[(/winrt](/windows/win32/midl/-winrt))。

### <a name="ignore-standard-include-path"></a>忽略標準包含路徑

忽略目前目錄和 INCLUDE 目錄[(/no_def_idir](/windows/win32/midl/-no-def-idir))。

### <a name="mktyplib-compatible"></a>MkTypLib 相容

強制相容 mktyplib.exe 版本 2.03[(/mktyplib203](/windows/win32/midl/-mktyplib203))。

### <a name="warning-level"></a>警告層級

選擇 MIDL 代碼錯誤的嚴格性 ([/W](/windows/win32/midl/-w))。

**Choices**

- **1**
- **1**
- **2**
- **3**
- **4**

### <a name="treat-warnings-as-errors"></a>警告視為錯誤

使 MIDL 將所有警告視為錯誤[(/WX](/windows/win32/midl/-wx))。

### <a name="suppress-startup-banner"></a>隱藏啟動橫幅

禁止顯示啟動橫幅和資訊消息[(/nologo)。](/windows/win32/midl/-nologo)

### <a name="c-compiler-char-type"></a>C 編譯器字元類型

指定將用於編譯生成的代碼的 C 編譯器的預設字元類型。 [(/字元](/windows/win32/midl/-char)簽名_未簽名_ascii7)。

**Choices**

- **已簽署**─ 已簽署
- **未簽署**─ 未簽署
- **阿西**- 阿西

### <a name="target-environment"></a>目標環境

指定要定位的環境[(/env](/windows/win32/midl/-env)臂 32_win32_ia64_x64)。

**Choices**

- **未設定**- 贏 32
- **微軟視窗 32 位**- Win32
- **微軟視窗 64 位元上 Itanium** - IA64
- **微軟視窗 ARM** - ARM
- **微軟視窗ARM64** - ARM64
- **微軟視窗 64 位 x64** - X64

### <a name="generate-stubless-proxies"></a>產生無存代理程式

生成具有物件介面[(/Oicf](/windows/win32/midl/-oi), [/Oif)](/windows/win32/midl/-oi)的擴展和無存根代理的完全解釋的存根。

### <a name="suppress-compiler-warnings"></a>隱藏編譯器警告

禁止編譯器警告消息[(/no_warn](/windows/win32/midl/-no-warn))。

### <a name="application-configuration-mode"></a>應用程式設定模式

允許在 IDL 檔中選擇 ACF 屬性[(/app_config](/windows/win32/midl/-app-config))。

### <a name="locale-id"></a>地區設定識別碼

指定輸入檔案、檔名和目錄路徑[(/lcid](/windows/win32/midl/-lcid) DECIMAL) 的 LCID。

### <a name="multi-processor-compilation"></a>多處理器編譯

同時運行多個實例。

## <a name="output-property-page"></a>輸出屬性頁

### <a name="output-directory"></a>輸出目錄

指定輸出目錄[(/out](/windows/win32/midl/-out) [目錄])。

### <a name="metadata-file"></a>中繼資料檔

指定生成的中繼資料檔[(/winmd](/windows/win32/midl/-winmd)檔名)的名稱。

### <a name="header-file"></a>標頭檔案

指定產生的標頭檔[(/h](/windows/win32/midl/-h)檔名)的名稱。

### <a name="dlldata-file"></a>DllData 檔案

指定 DLLDATA 檔案[(/dlldata](/windows/win32/midl/-dlldata)檔案名稱) 的名稱。

### <a name="iid-file"></a>IID 檔案

指定介面識別碼[(/iid](/windows/win32/midl/-iid)檔名) 的名稱。

### <a name="proxy-file"></a>代理檔案

指定代理檔[(/代理](/windows/win32/midl/-proxy)檔案名稱)的名稱。

### <a name="generate-type-library"></a>產生類型庫

指定不生成類型庫(\/notlb= 否)。

### <a name="type-library"></a>類型庫

指定類型函式庫檔[(/tlb](/windows/win32/midl/-tlb)檔名) 的名稱。

### <a name="generate-client-stub-files"></a>產生用戶端存取根檔案

僅生成用戶端存根檔[(/用戶端](/windows/win32/midl/-client)[存根]無)。

**Choices**

- **存根**- 存根
- **無**- 無

### <a name="generate-server-stub-files"></a>組建伺服器存取根檔案

僅生成伺服器存根檔[(/伺服器](/windows/win32/midl/-server)[存根]無)。

**Choices**

- **存根**- 存根
- **無**- 無

### <a name="client-stub-file"></a>用戶端存取檔案

指定用戶端存根檔[(/cstub](/windows/win32/midl/-cstub) [檔案])。

### <a name="server-stub-file"></a>伺服器存根檔案

指定伺服器存根檔[(/stub](/windows/win32/midl/-sstub) [檔案])。

### <a name="type-library-format"></a>型態庫格式

指定類型庫檔案格式(*/舊\tlb_/newtlb*)。

**Choices**

- **新格式**- 新格式
- **舊格式**- 舊格式

## <a name="advanced-property-page"></a>進階屬性頁

### <a name="c-preprocess-options"></a>C 預處理選項

指定交換機以傳遞給 C 編譯器預處理器[(/cpp_opt](/windows/win32/midl/-cpp-opt)交換機)。

### <a name="undefine-preprocessor-definitions"></a>取消前置處理器的定義

指定一個或多個未定義,包括 MIDL 宏[(/U[](/windows/win32/midl/-U)宏])。

### <a name="enable-error-checking"></a>開啟錯誤檢查

選擇錯誤檢查選項(*/錯誤全部=無])。

**Choices**

- **開啟自訂**- 所有
- **全部**- 所有
- **無**- 無

### <a name="check-allocations"></a>檢查配置

檢查記憶體不足錯誤[(/錯誤](/windows/win32/midl/-error)分配)。

### <a name="check-bounds"></a>檢查邊界

檢查大小與傳輸長度規格[(/錯誤](/windows/win32/midl/-error)bounds_check)。

### <a name="check-enum-range"></a>檢查枚舉範圍

檢查枚舉值是否在允許範圍內[(/錯誤](/windows/win32/midl/-error)枚舉)。

### <a name="check-reference-pointers"></a>檢查參考指標

檢查引用指標為非空[(/錯誤](/windows/win32/midl/-error)參考)。

### <a name="check-stub-data"></a>檢查存根資料

發出其他檢查,檢查伺服器端存根數據的有效性[(/錯誤](/windows/win32/midl/-error)stub_data)。

### <a name="prepend-with-abi-namespace"></a>使用「ABI」命名空間進行預寫

將「ABI」命名空間準備到所有類型的。  [(/ns_prefix](/windows/win32/midl/-ns-prefix))。

### <a name="validate-parameters"></a>驗證參數

生成其他資訊以驗證參數[(/robust](/windows/win32/midl/-robust) | [/no_robust](/windows/win32/midl/-no-robust))。

### <a name="struct-member-alignment"></a>結構成員對齊

指定目標系統中結構 (/ZpN) 中的封裝水準。

**Choices**

- **未設定**- 未設定
- **1 位元組**- Zp1
- **2 位元組**- Zp2
- **4 位元組**- Zp4
- **8 位元組**- Zp8

### <a name="redirect-output"></a>重定向輸出

將輸出從螢幕重定向到檔[(/o](/windows/win32/midl/-o)檔案)。

### <a name="minimum-target-system"></a>最小目標系統

設置最小目標系統[(/目標](/windows/win32/midl/-target)STRING)。
