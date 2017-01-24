---
title: "編譯器錯誤 CS1032 | Microsoft Docs"
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
  - "CS1032"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1032"
ms.assetid: fe318a6c-4403-4b9b-b3d8-753ec31c00ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS1032
於檔案第一個語彙基元後無法定義或取消定義前置處理器符號  
  
 `#define` 和 `#undef`[前置處理器指示詞](../Topic/C%23%20Preprocessor%20Directives.md)必須用於程式開頭的任何其他關鍵字之前 \(例如命名空間宣告中所使用的關鍵字\)。  
  
 下列範例會產生 CS1032：  
  
```  
// CS1032.cs namespace x { public class clx { #define a   // CS1032, put before namespace public static void Main() { } } }  
```