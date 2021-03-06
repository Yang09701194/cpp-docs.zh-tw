---
title: /Zc (一致性)
ms.date: 03/06/2018
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 4422524deab2a749c96d5e967bc3223d0c9c9873
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438664"
---
# <a name="zc-conformance"></a>/Zc (一致性)

您可以使用 **/zc**編譯器選項來指定標準或 Microsoft 特定的編譯器行為。

## <a name="syntax"></a>語法

> **/Zc：** _option_{，_option_}

## <a name="remarks"></a>備註

當 Visual Studio 將擴充功能實作為 C 或C++與標準不相容時，您可以使用 `/Zc` 一致性選項來指定符合標準或 Microsoft 特定的行為。 針對某些選項，Microsoft 特有的行為是預設值，以防止對現有程式碼進行大規模的重大變更。 在其他情況下，預設值是標準行為，在此情況下，安全性、效能或相容性的改善會超過中斷性變更的成本。 在較新版本的 Visual Studio 中，每個一致性選項的預設設定可能會變更。 如需每個一致性選項的詳細資訊，請參閱特定選項的主題。 [/Permissive-](permissive-standards-conformance.md)編譯器選項會隱含地將預設未設定的一致性選項設定為其一致的設定。

這些是 `/Zc` 的編譯器選項：

|選項|行為|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|啟用 c + + 17 過度對齊的動態配置（在 c + + 17 中預設為開啟）。|
|[自動\[-\]](zc-auto-deduce-variable-type.md)|強制執行 `auto` 的C++新標準意義（預設為開啟）。|
|[__cplusplus\[-\]](zc-cplusplus.md)|啟用 **__cplusplus**宏以報告支援的標準（預設為關閉）。|
|[externConstexpr\[-\]](zc-externconstexpr.md)|啟用 `constexpr` 變數的外部連結（預設為關閉）。|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|強制執行C++標準 `for` 範圍規則（預設為開啟）。|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|啟用必要函式的隱含 `noexcept` （預設為開啟）。|
|[內嵌\[-\]](zc-inline-remove-unreferenced-comdat.md)|如果未參考的函式或資料已 COMDAT，或是只有內部連結（預設為關閉），請將其移除。|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|強制執行 c + + 17 noexcept 規則（在 c + + 17 或更新版本中預設為開啟）。|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|UDT 暫存不會系結至非 const 左值參考（預設為關閉）。|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|強制執行C++標準明確類型轉換規則（預設為關閉）。|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|啟用 c + + 14 全域大小的解除配置函式（預設為開啟）。|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|停用字串常值以 `char*` 或 `wchar_t*` 轉換（預設為關閉）。|
|[三元\[-\]](zc-ternary.md)|強制執行運算元類型的條件運算子規則（預設為關閉）。|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|啟用安全線程本機靜態初始化（預設為開啟）。|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|假設 `operator new` 在失敗時擲回（預設為關閉）。|
|[三並詞\[-\]](zc-trigraphs-trigraphs-substitution.md)|啟用三並詞（預設為已淘汰，關閉）。|
|[twoPhase](zc-twophase.md)|使用不符合標準的範本剖析行為（預設為符合）。|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` 是原生類型，而非 typedef （預設為開啟）。|

如需 Visual C++ 中一致性問題的詳細資訊，請參閱 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)。

## <a name="see-also"></a>另請參閱

[MSVC 編譯器選項](compiler-options.md)<br/>
[MSVC 編譯器命令列語法](compiler-command-line-syntax.md)
