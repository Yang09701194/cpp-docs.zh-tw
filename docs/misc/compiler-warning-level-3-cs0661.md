---
title: "編譯器警告 (層級 3) CS0661 | Microsoft Docs"
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
  - "CS0661"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0661"
ms.assetid: c218665e-5947-40bb-b633-d268483e6522
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器警告 (層級 3) CS0661
'class' 定義了運算子 \=\= 或運算子 \!\=，但並沒有覆寫 Object.GetHashCode\(\)  
  
 編譯器偵測到使用者定義的相等或不等比較運算子，但不覆寫 **GetHashCode** 函式。 使用者定義的相等或不等比較運算子暗示您也需要覆寫 **GetHashCode** 函式。  
  
 下列範例會產生 CS0661：  
  
```  
// CS0661.cs // compile with: /W:3 class Test   // CS0661 { public static bool operator == (object o, Test t) { return true; } public static bool operator != (object o, Test t) { return true; } public override bool Equals(object o) { return true; } // uncomment the GetHashCode function to resolve // public override int GetHashCode() // { //    return 0; // } public static void Main() { } }  
```