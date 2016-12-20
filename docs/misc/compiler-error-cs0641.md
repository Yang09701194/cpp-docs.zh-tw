---
title: "編譯器錯誤 CS0641 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0641"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0641"
ms.assetid: 5bcdb11a-fefd-4c71-9b31-4c4f719633f3
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS0641
'attribute' : 屬性只在衍生自 System.Attribute 的類別上有效  
  
 使用過的屬性，只能用在衍生自 **System.Attribute** 的類別。  
  
 下列範例會產生 CS0641：  
  
```  
// CS0641.cs using System; [AttributeUsage(AttributeTargets.All)] public class NonAttrClass   // CS0641 // try the following line instead // public class NonAttrClass : Attribute { } class MyClass { public static void Main() { } }  
```