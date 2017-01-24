---
title: "逐步解說：顯示智慧標籤 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "編輯器 [Visual Studio SDK], 新增 - 智慧標籤"
ms.assetid: 10bb4f69-b259-41f0-b91a-69b04385d9a5
caps.latest.revision: 31
caps.handback.revision: 31
manager: "douge"
---
# 逐步解說：顯示智慧標籤
智慧標籤已取代為燈泡。 請參閱 [逐步解說: 顯示燈泡建議](../Topic/Walkthrough:%20Displaying%20Light%20Bulb%20Suggestions.md)。  
  
 智慧標籤是文字上展開以顯示一組動作的標籤。 例如，在 Visual Basic 或 Visual C\# 專案中，當您重新命名識別項 \(例如變數名稱\) 時，會在這個字組下方出現紅線。 當您將指標移至底線上方時，會在指標附近顯示按鈕。 如果您按一下該按鈕，則會顯示建議的動作 \(例如，\[將 IsRead 重新命名為 IsReady\]\)。 如果您按一下該動作，專案中的所有 **IsRead** 參考都會重新命名為 **IsReady**。  
  
 雖然智慧標籤是編輯器中 IntelliSense 實作的一部分，但是您可以透過子類別化 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag>，然後實作 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> 介面和 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider> 介面，來實作智慧標籤。  
  
> [!NOTE]
>  其他類型的標籤可以透過類似的方式實作。  
  
 下列逐步解說示範如何建立智慧標籤，而智慧標籤出現在目前字組上，而且有兩項建議的動作：\[轉換為大寫\] 和 \[轉換為小寫\]。  
  
## 必要條件  
 若要依照本逐步解說執行作業，您必須安裝 Visual Studio SDK。 如需詳細資訊，請參閱[Visual Studio SDK](../Topic/Visual%20Studio%20SDK.md)。  
  
## Managed Extensibility Framework \(MEF\)  
  
#### 建立 MEF 專案  
  
1.  建立編輯器分類器專案。 將方案命名為 `SmartTagTest`。  
  
2.  在 VSIX 資訊清單編輯器中，開啟 source.extension.vsixmanifest 檔案。  
  
3.  確定 \[資產\] 區段包含 `Microsoft.VisualStudio.MefComponent` 類型、\[來源\] 設定為 `A project in current solution`，並將 \[專案\] 設定為 SmartTagTest.dll。  
  
4.  儲存並關閉 source.extension.vsixmanifest。  
  
5.  將下列參考加入專案中，並將 **CopyLocal** 設定為 `false`：  
  
     Microsoft.VisualStudio.Language.Intellisense  
  
6.  刪除現有類別檔案。  
  
## 實作智慧標籤的標記者  
  
#### 實作智慧標籤的標記者  
  
1.  加入類別檔案，並將它命名為 `TestSmartTag`。  
  
2.  加入下列匯入：  
  
     [!code-cs[VSSDKSmartTagTest#1](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_1.cs)]
     [!code-vb[VSSDKSmartTagTest#1](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_1.vb)]  
  
3.  加入名為 `TestSmartTag` 且繼承自 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag> 的類別。  
  
     [!code-cs[VSSDKSmartTagTest#2](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_2.cs)]
     [!code-vb[VSSDKSmartTagTest#2](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_2.vb)]  
  
4.  加入這個類別的建構函式，以使用 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType> 的 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType> 來呼叫基底建構函式，這樣會在某個字組的第一個字元下方出現藍線。  \(如果您使用 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTagType>，會在這個字組的最後一個字元下方出現紅線\)。  
  
     [!code-cs[VSSDKSmartTagTest#3](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_3.cs)]
     [!code-vb[VSSDKSmartTagTest#3](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_3.vb)]  
  
5.  加入名為 `TestSmartTagger` 的類別，這個類別繼承自類型 `TestSmartTag` 的 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601>，並實作 <xref:System.IDisposable>。  
  
     [!code-cs[VSSDKSmartTagTest#4](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_4.cs)]
     [!code-vb[VSSDKSmartTagTest#4](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_4.vb)]  
  
6.  在標記者類別中加入下列私用欄位。  
  
     [!code-cs[VSSDKSmartTagTest#5](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_5.cs)]
     [!code-vb[VSSDKSmartTagTest#5](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_5.vb)]  
  
7.  加入建構函式，以設定私用欄位並訂閱 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 事件。  
  
     [!code-cs[VSSDKSmartTagTest#6](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_6.cs)]
     [!code-vb[VSSDKSmartTagTest#6](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_6.vb)]  
  
8.  實作 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A>，以為目前字組建立標籤。 \(這種方法也會呼叫稍後說明的私用方法 `GetSmartTagActions`\)。  
  
     [!code-cs[VSSDKSmartTagTest#7](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_7.cs)]
     [!code-vb[VSSDKSmartTagTest#7](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_7.vb)]  
  
9. 加入 `GetSmartTagActions` 方法來設定智慧標籤動作。 在後面的步驟中會實作動作本身。  
  
     [!code-cs[VSSDKSmartTagTest#8](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_8.cs)]
     [!code-vb[VSSDKSmartTagTest#8](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_8.vb)]  
  
10. 宣告 `SmartTagsChanged` 事件。  
  
     [!code-cs[VSSDKSmartTagTest#9](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_9.cs)]
     [!code-vb[VSSDKSmartTagTest#9](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_9.vb)]  
  
11. 實作 `OnLayoutChanged` 事件處理常式來引發 `TagsChanged` 事件，以呼叫 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A>。  
  
     [!code-cs[VSSDKSmartTagTest#10](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_10.cs)]
     [!code-vb[VSSDKSmartTagTest#10](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_10.vb)]  
  
12. 實作 <xref:System.IDisposable.Dispose%2A> 方法，以從 <xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> 事件中取消訂閱它。  
  
     [!code-cs[VSSDKSmartTagTest#11](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_11.cs)]
     [!code-vb[VSSDKSmartTagTest#11](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_11.vb)]  
  
## 實作智慧標籤標記者提供者  
  
#### 實作智慧標籤標記者提供者  
  
1.  加入名為 `TestSmartTagTaggerProvider` 且繼承自 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider> 的類別。 使用 <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> 為 "text"、<xref:Microsoft.VisualStudio.Utilities.OrderAttribute> 為 Before\="default" 且 <xref:Microsoft.VisualStudio.Text.Tagging.TagTypeAttribute> 為 <xref:Microsoft.VisualStudio.Language.Intellisense.SmartTag>，來匯出它。  
  
     [!code-cs[VSSDKSmartTagTest#12](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_12.cs)]
     [!code-vb[VSSDKSmartTagTest#12](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_12.vb)]  
  
2.  匯入 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> 作為屬性。  
  
     [!code-cs[VSSDKSmartTagTest#13](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_13.cs)]
     [!code-vb[VSSDKSmartTagTest#13](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_13.vb)]  
  
3.  實作 <xref:Microsoft.VisualStudio.Text.Tagging.IViewTaggerProvider.CreateTagger%2A> 方法。  
  
     [!code-cs[VSSDKSmartTagTest#14](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_14.cs)]
     [!code-vb[VSSDKSmartTagTest#14](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_14.vb)]  
  
## 實作智慧標籤動作  
  
#### 實作智慧標籤動作  
  
1.  建立兩個類別：第一個命名為 `UpperCaseSmartTagAction`，第二個則命名為 `LowerCaseSmartTagAction`。 這兩個類別都會實作 <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagAction>。  
  
     [!code-cs[VSSDKSmartTagTest#15](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_15.cs)]
     [!code-vb[VSSDKSmartTagTest#15](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_15.vb)]  
  
     [!code-cs[VSSDKSmartTagTest#16](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_16.cs)]
     [!code-vb[VSSDKSmartTagTest#16](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_16.vb)]  
  
 這兩個類別相同，差別在於其中一個會呼叫 <xref:System.String.ToUpper%2A>，另一個會呼叫 <xref:System.String.ToLower%2A>。 下列步驟僅涵蓋大寫動作類別，但您必須實作這兩個類別。 使用實作大寫動作的步驟，作為實作小寫動作的模式。  
  
1.  宣告一組私用欄位。  
  
     [!code-cs[VSSDKSmartTagTest#17](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_17.cs)]
     [!code-vb[VSSDKSmartTagTest#17](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_17.vb)]  
  
2.  加入可設定欄位的建構函式。  
  
     [!code-cs[VSSDKSmartTagTest#18](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_18.cs)]
     [!code-vb[VSSDKSmartTagTest#18](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_18.vb)]  
  
3.  依照下列所示來實作屬性。  
  
     [!code-cs[VSSDKSmartTagTest#19](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_19.cs)]
     [!code-vb[VSSDKSmartTagTest#19](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_19.vb)]  
  
4.  將範圍中的文字取代為其大寫對等項目，以實作 <xref:Microsoft.VisualStudio.Language.Intellisense.ISmartTagAction.Invoke%2A> 方法。  
  
     [!code-cs[VSSDKSmartTagTest#20](../misc/codesnippet/CSharp/walkthrough-displaying-smarttags_20.cs)]
     [!code-vb[VSSDKSmartTagTest#20](../misc/codesnippet/VisualBasic/walkthrough-displaying-smarttags_20.vb)]  
  
## 建置和測試程式碼  
 若要測試這段程式碼，請建置 SmartTagTest 方案，並在實驗執行個體中執行它。  
  
#### 建置並測試 SmartTagTest 方案  
  
1.  建置方案。  
  
2.  當您在偵錯工具中執行這個專案時，會具現化第二個 Visual Studio 執行個體。  
  
3.  建立文字檔，並輸入一些文字。  
  
     應該會在文字之第一個字組的第一個字母下方顯示藍線。  
  
4.  將指標移至藍線上方。  
  
     應該會在指標附近顯示按鈕。  
  
5.  當您按一下該按鈕時，應該會顯示兩項建議的動作：\[轉換為大寫\] 和 \[轉換為小寫\]。 如果您按一下第一個動作，則應該會將目前字組中的所有文字都轉換為大寫。 如果您按一下第二個動作，則應該會將所有文字都轉換為小寫。  
  
## 請參閱  
 [逐步解說: 將內容類型連結至檔案名稱副檔名](../Topic/Walkthrough:%20Linking%20a%20Content%20Type%20to%20a%20File%20Name%20Extension.md)