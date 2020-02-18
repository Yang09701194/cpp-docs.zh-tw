---
title: 快速入門：C/C++ 程式碼分析
description: 在 Visual Studio 的程式C++代碼上執行靜態分析，以偵測常見的編碼問題和瑕疵。
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- C/C++ code analysis
- code analysis,C/C++
ms.openlocfilehash: 5ee8f702ddf489732f664ae73eed75b18dc46e86
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418778"
---
# <a name="quickstart-code-analysis-for-cc"></a>快速入門：C/C++ 的程式碼分析

您可以在 C 或 C++ 程式碼上定期執行程式碼分析，以改善您的應用程式品質。 這可協助您尋找常見的問題、良好的程式設計作法違規狀況，或偵測難以透過測試發現的缺失。 程式碼分析警告與編譯器錯誤和警告不同，因為程式碼分析會搜尋有效的特定程式碼模式，但仍然可以為您或使用您程式碼的其他人建立問題。

## <a name="configure-rule-sets-for-a-project"></a>設定專案的規則集

1. 在**方案總管**中，開啟專案名稱的快捷方式功能表，然後選擇 [**屬性**]。

1. （選擇性 **）在 [** 設定] 和 [**平臺**] 清單中，選擇 [組建設定] 和 [目標平臺]。

1. 若要在每次使用選取的設定建立專案時執行程式碼分析，請選取 [**在組建上啟用程式碼分析**] 核取方塊。 您也可以開啟 [**分析**] 功能表，然後選擇 [在*專案名稱***上執行程式碼分析**] 或 [檔案**上執行**程式碼分析]，手動執行程式碼分析。

1. 選擇您想要使用的[規則集](using-rule-sets-to-specify-the-cpp-rules-to-run.md)，或建立[自訂規則集](using-rule-sets-to-specify-the-cpp-rules-to-run.md#to-create-a-rule-set-in-a-text-editor)。 如果使用 LLVM/clang-cl，請參閱[在 Visual Studio 中使用 clang](../code-quality/clang-tidy.md) ，以設定 clang 整齊的分析選項。

### <a name="standard-cc-rule-sets"></a>標準 C/C++ 規則集

Visual Studio 包含兩組標準的原生程式碼規則：

|規則集|描述|
|--------------|-----------------|
|Microsoft 原生最小建議規則|此規則集的重點在於機器碼中最關鍵的問題，包括可能的安全性漏洞和應用程式損毀。 您應該在為原生專案建立的任何自訂規則集中，包含此規則集。|
|Microsoft 原生建議規則|此規則集涵蓋廣泛的問題。 它在 Microsoft 原生最小建議規則中包含所有規則。|

## <a name="run-code-analysis"></a>執行程式碼分析

在 [專案屬性] 頁面的 [程式碼分析] 頁面上，您可以設定在每次建立專案時執行程式碼分析。 您也可以手動執行程式碼分析。

若要針對方案執行程式碼分析：

- 在 [**建立**] 功能表中，選擇 [**針對方案執行程式碼分析**]。

若要針對專案執行程式碼分析：

1. 在 方案總管中，選取專案的名稱。

1. 在 [**建立**] 功能表中，選擇 [針對*專案名稱***執行程式碼分析**]。

若要對檔案執行程式碼分析：

1. 在 方案總管中，選取檔案名。

1. 在 [**建立**] 功能表中，選擇 [**在檔案上執行程式碼分析**] 或按**Ctrl + Shift + Alt + F7**。

   編譯專案或方案並執行程式碼分析。 結果會出現在錯誤清單中。

## <a name="analyze-and-resolve-code-analysis-warnings"></a>分析和解決程式碼分析警告

若要分析特定警告，請在 錯誤清單中選擇警告的標題。 隨即展開警告以顯示問題的其他資訊。 如果可能的話，程式碼分析會顯示導致警告的行號和分析邏輯。 如需警告的詳細資訊，包括問題的可能解決方案，請選擇警告識別碼以顯示其對應的線上說明主題。

當您選取警告時，會在 [Visual Studio 程式碼編輯器] 中反白顯示造成警告的程式程式碼。

在您了解問題之後，就可以在程式碼中解決問題。 然後，重新執行程式碼分析，以確定警告不會再出現在錯誤清單中，而且您的修正尚未引發任何新的警告。

## <a name="suppress-code-analysis-warnings"></a>隱藏程式碼分析警告

有時候您可能決定不修正程式碼分析警告。 您可能會判斷解決這項警告需要太多重新編碼，而在任何實際實作程式碼時會有問題發生的可能性。 或是，您可能會認為警告中使用的分析對於特定內容是不適當的。 您可以隱藏個別的警告，使其不會再出現在錯誤清單中。

### <a name="to-suppress-a-warning"></a>若要隱藏警告

1. 如果未顯示詳細資訊，請選擇警告標題以展開它。

1. 選擇警告下方的 [動作] 連結。

1. 選擇 [**隱藏訊息**]，然後選擇 [**在來源**]。

   隱藏訊息會插入隱藏程式程式碼警告的 `#pragma warning (disable:[warning ID])`。

## <a name="create-work-items-for-code-analysis-warnings"></a>建立程式碼分析警告的工作專案

若要記錄來自 Visual Studio 的錯誤，您可以使用工作項目追蹤功能。 若要使用這項功能，您必須連接到 Team Foundation Server 的執行個體。

### <a name="to-create-a-work-item-for-one-or-more-cc-code-warnings"></a>建立一或多個 C/C++ 程式碼警告的工作項目

1. 在 錯誤清單中，展開並選取警告

1. 在警告的快捷方式功能表上，選擇 [**建立工作專案**]，然後選擇 [工作專案類型]。

1. Visual Studio 會建立選定警告的單一工作項目，並在 IDE 的文件視窗中顯示工作項目。

1. 新增任何其他資訊，然後選擇 [**儲存工作專案**]。

## <a name="search-and-filter-code-analysis-results"></a>搜尋和篩選程式代碼分析結果

您可以在多個專案方案中，搜尋警告訊息的長清單，也可以篩選警告。

- **若要依標題或警告識別碼篩選警告**：在 [搜尋] 方塊中輸入關鍵字。

- **若要依嚴重性篩選警告**：根據預設，系統會將**警告**的嚴重性指派給程式碼分析訊息。 在自訂規則集中，您可以將一或多個訊息的嚴重性指派為 [**錯誤**]。 在**錯誤清單**的 [**嚴重性**] 資料行上，選擇下拉箭號，然後選取篩選圖示。 選擇 [**警告**] 或 [**錯誤**]，只顯示指派給個別嚴重性的訊息。 選擇 [**全選**] 以顯示所有訊息。

## <a name="see-also"></a>另請參閱

- [C/的程式碼分析C++](../code-quality/code-analysis-for-c-cpp-overview.md)
