---
title: /Zc:forScope (強制 for 迴圈範圍中的一致性)
ms.date: 03/06/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
ms.openlocfilehash: 7f98667d3a771994d1b4e54b429f42cb566c102c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316024"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (強制 for 迴圈範圍中的一致性)

用來搭配 Microsoft 擴充功能 ( [/Ze](../../cpp/for-statement-cpp.md) ) 實作[for](za-ze-disable-language-extensions.md)迴圈的標準 C++ 行為。

## <a name="syntax"></a>語法

> **/Zc:forScope**[**-**]

## <a name="remarks"></a>備註

標準行為是讓 **for** 迴圈的初始設定式在 **for** 迴圈之後時超出範圍。 在 **/Zc:forScope-** 與 [/Ze](za-ze-disable-language-extensions.md)下， **for** 迴圈的初始設定式會維持在範圍內，直到本機範圍結束為止。

**/Zc: forscope**選項預設為開啟。 **/Zc: forscope**不會受到影響時[/permissive--](permissive-standards-conformance.md)指定選項。

**/Zc:forScope-** 選項已遭取代，並將在未來版本中移除。 使用 **/Zc:forScope-** 會產生取代警告 D9035。

下列程式碼會在 **/Ze** 下編譯，而非在 **/Za**下：

```cpp
// zc_forScope.cpp
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp
// C2065, D9035 expected
int main() {
    // Compile by using cl /Zc:forScope- zc_forScope.cpp
    // to compile this non-standard code as-is.
    // Uncomment the following line to resolve C2065 for /Za.
    // int i;
    for (int i = 0; i < 1; i++)
        ;
    i = 20;   // i has already gone out of scope under /Za
}
```

若您使用 **/Zc:forScope-**，當變數因為前一個範圍中所做的宣告而在範圍內時，會產生警告 C4288 (預設為關閉)。 若要示範這點，請移除範例程式碼中的 `//` 字元，以宣告 `int i`。

您可使用 **conform** pragma 來修改 [/Zc:forScope](../../preprocessor/conform.md) 的執行階段行為。

若在具備現有 .pch 檔的專案中使用 **/Zc:forScope-** ，會產生警告、忽略 **/Zc:forScope-** ，並使用現有的 .pch 檔案繼續編譯。 如果您想要產生新的.pch 檔案，使用[/Yc （建立先行編譯標頭檔）](yc-create-precompiled-header-file.md)。

如需 Visual C++ 中一致性問題的詳細資訊，請參閱 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資訊，請參閱 <<c0> [ 設定C++Visual Studio 中的編譯器和組建屬性](../working-with-project-properties.md)。</c0>

1. 選取 **組態屬性** > **C /C++** > **語言**屬性頁。

1. 修改 [強制在 For 迴圈範圍中一致]  屬性。

### <a name="to-set-this-compiler-option-programmatically"></a>若要以程式方式設定這個編譯器選項

- 請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>。

## <a name="see-also"></a>另請參閱

[/Zc (一致性)](zc-conformance.md)<br/>
[/Za、/Ze (停用語言延伸模組)](za-ze-disable-language-extensions.md)<br/>
