---
title: "編譯器錯誤 CS0543 | Microsoft Docs"
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
  - "CS0543"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0543"
ms.assetid: f85e09a7-0e08-4dea-8f64-218c0876e4f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS0543
'enumeration' : 就其類型而言，此列舉值過大  
  
 指派給[列舉](../Topic/enum%20\(C%23%20Reference\).md)中某個項目的值超過資料類型的範圍。  
  
 下列範例會產生 CS0543：  
  
```  
// CS0543.cs namespace x { enum I : byte {a = 255, b, c}   // CS0543 public class clx { public static int Main() { return 0; } } }  
```