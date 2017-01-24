---
title: "編譯器錯誤 CS0101 | Microsoft Docs"
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
  - "CS0101"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0101"
ms.assetid: edb5246b-c16b-4845-bb2d-0ef769d014c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS0101
命名空間 'namespace' 已包含 'type' 的定義  
  
 [命名空間](../Topic/namespace%20\(C%23%20Reference\).md)有重複的識別項。 請重新命名或刪除其中一個重複的識別項。 如需詳細資訊，請參閱[命名空間](../Topic/Namespaces%20\(C%23%20Programming%20Guide\).md)。  
  
 下列範例會產生 CS0101：  
  
```  
// CS0101.cs namespace MyNamespace { public class MyClass { static public void Main() { } } public class MyClass   // CS0101 { } }  
```