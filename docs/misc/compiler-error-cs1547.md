---
title: "編譯器錯誤 CS1547 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1547"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1547"
ms.assetid: 40029557-076a-47d8-aabc-d86c56a846d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS1547
在此內容中不可使用關鍵字 'void'  
  
 編譯器偵測到無效地使用 [void](../Topic/void%20\(C%23%20Reference\).md) 關鍵字。  
  
 下列範例會產生 CS1547：  
  
```  
// CS1547.cs public class MyClass { void BadMethod() { void i;   // CS1547, cannot have variables of type void } public static void Main() { } }  
```