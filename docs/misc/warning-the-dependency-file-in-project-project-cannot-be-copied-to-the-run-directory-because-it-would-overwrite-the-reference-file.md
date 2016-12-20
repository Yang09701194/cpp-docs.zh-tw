---
title: "警告: 無法將專案 &#39;project&#39; 中的相依性 &#39;file&#39; 複製至執行目錄，因為它會覆寫參考 &#39;file&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.copy_version_warning"
ms.assetid: 116819f3-a4d4-48b5-9e71-7c54660d38ef
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 警告: 無法將專案 &#39;project&#39; 中的相依性 &#39;file&#39; 複製至執行目錄，因為它會覆寫參考 &#39;file&#39;
相依性之間發生衝突；若要執行應用程式，應該將多個同名的相異組件檔複製到 bin 目錄。 由於其中一個相依性是主要參考，因此執行目錄可以解決衝突。  
  
 按兩下此工作清單項目將可帶您前往發生衝突的主要參考節點。  
  
 當您有相依性衝突時，就會出現這個警告，不過藉由將其中一個衝突的相依性加入作為參考，即可解決問題。 或者，您也可以有版本 1 參考，再加入本身參考第一個參考版本 2 的第二個參考。  
  
 換句話說，此錯誤的發生原因在於方案中的專案彼此參考，但參考建立時是作為檔案參考 \(使用 \[加入參考\][](http://msdn.microsoft.com/zh-tw/2feb0fe2-0805-4cc9-8cba-b0315849dfb7) 對話方塊中的 \[瀏覽\] 按鈕\)，而不是專案對專案間的參考 \(使用 \[加入參考\] 對話方塊中的 \[專案\] 索引標籤\)。 專案對專案間的參考優點是，它會在組建系統中建立專案之間的相依性，如此一來，如果自上次建置的參考專案已變更，則會建置相依專案。 檔案參考不會建立組建相依性，因此可以建置參考專案而不需建置相依專案，且參考可能會過時；專案可以參考先前建置的專案版本。 這會導致在 bin 目錄中需要單一 DLL 的數個版本，但這不可能達成，因此會產生這個錯誤訊息。  
  
 每當 bin 目錄中有衝突，而且應用程式可能無法正常運作時，就會出現此訊息。 即使您已解決此問題，因為專案系統無法判斷該版相依性是否會搭配所有元件正確運作，所以仍會出現這個警告。  
  
 **更正這個錯誤**  
  
-   將一個 \(或零個\) 組件檔複製到 bin 目錄，您可以將組件檔放入全域組件快取來達成目的。 全域組件快取會解決檔案名稱衝突。 因為 Common Language Runtime 知道如何在全域組件快取中尋找組件，所以不會對組件檔進行任何本機複製。 如需詳細資訊，請參閱 [使用組件和全域組件快取](../Topic/Working%20with%20Assemblies%20and%20the%20Global%20Assembly%20Cache.md) 與 [錯誤: 無法將專案 'project' 中的相依性 'file' 複製至執行目錄，因為它會和相依性 'file' 衝突](../misc/error-the-dependency-file-in-project-project-cannot-be-copied-to-the-run-directory-because-it-would-conflict-with-dependency-file.md)。  
  
## 請參閱  
 [管理專案中的參考](../Topic/Managing%20references%20in%20a%20project.md)   
 [全域組件快取](../Topic/Global%20Assembly%20Cache.md)   
 [如何：建立和移除專案相依性](../Topic/How%20to:%20Create%20and%20Remove%20Project%20Dependencies.md)