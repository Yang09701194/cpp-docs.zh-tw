---
title: "編譯器錯誤 CS0748 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0748"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0748"
ms.assetid: da1935af-a5ea-41f4-84ae-58559b750566
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS0748
Lambda 參數用法不一致；參數類型必須全部為明確類型或全部為隱含類型。  
  
 如果 Lambda 運算式有多個輸入參數，則不能有某些參數使用隱含類型但其他參數使用明確類型的情況。  
  
### 更正這個錯誤  
  
1.  請提供所有輸入參數隱含類型，或是讓它們全為明確類型。  
  
## 範例  
 下列程式碼會產生 CS0748，因為在 Lambda 運算式中，只有 `alpha` 具有明確類型：  
  
```  
// cs0748.cs class CS0748 { delegate double D(int x, int y); D d = (int alpha, beta) => { return beta / alpha; }; // CS0748 }  
```  
  
## 請參閱  
 [Lambda 運算式](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md)