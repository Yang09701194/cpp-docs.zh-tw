---
title: "編譯器錯誤 CS1512 | Microsoft Docs"
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
  - "CS1512"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1512"
ms.assetid: 50740d85-598d-478f-bfe3-e8c2e1a02ab8
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS1512
在目前的內容中無法使用關鍵字 'base'  
  
 [base](../Topic/base%20\(C%23%20Reference\).md) 關鍵字已使用在方法、屬性或建構函式之外。  
  
 下列範例會產生 CS1512：  
  
```  
// CS1512.cs using System; class Base {} class CMyClass : Base { private String xx = base.ToString();   // CS1512 // Try putting this initialization in the constructor instead: // public CMyClass() // { //    xx = base.ToString(); // } public static void Main() { CMyClass z = new CMyClass(); } }  
```