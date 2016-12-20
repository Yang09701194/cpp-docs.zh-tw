---
title: "編譯器錯誤 CS0030 | Microsoft Docs"
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
  - "CS0030"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0030"
ms.assetid: 3c9bd3f9-dea2-46dd-be1e-46c843ffd3de
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS0030
無法將類型 'type' 轉換為 'type'  
  
 您必須提供轉換常式，以支援特定運算子多載。 如需詳細資訊，請參閱[轉換運算子](../Topic/Conversion%20Operators%20\(C%23%20Programming%20Guide\).md)。  
  
 下列範例會產生 CS0030：  
  
```  
// CS0030.cs namespace x { public class iii { /* public static implicit operator iii(int aa) { return null; } public static implicit operator int(iii aa) { return 0; } */ public static iii operator ++(iii aa) { return (iii)0;   // CS0030 // uncomment the conversion routines to resolve CS0030 } public static void Main() { } } }  
```