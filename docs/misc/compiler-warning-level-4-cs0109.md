---
title: "編譯器警告 (層級 4) CS0109 | Microsoft Docs"
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
  - "CS0109"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0109"
ms.assetid: 42ac72e5-5081-4e8b-b2cf-5e10c1606676
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器警告 (層級 4) CS0109
成員 'member' 並未隱藏所繼承的成員。 不需要 new 關鍵字  
  
 類別宣告已包含 [new](../Topic/new%20\(C%23%20Reference\).md) 關鍵字，即使宣告未覆寫基底類別中的現有宣告。 您可以刪除 **new** 關鍵字。  
  
 下列範例會產生 CS0109：  
  
```  
// CS0109.cs // compile with: /W:4 namespace x { public class a { public int i; } public class b : a { public new int i; public new int j;   // CS0109 public static void Main() { } } }  
```