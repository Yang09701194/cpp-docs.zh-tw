---
title: "編譯器警告 (層級 2) CS0252 | Microsoft Docs"
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
  - "CS0252"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0252"
ms.assetid: ff82fbac-01cf-4ae9-b6a0-3aa990096b46
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器警告 (層級 2) CS0252
可能誤用了參考比較; 若您是要做數值比較，請將左邊轉換為類型 'type'  
  
 編譯器正在進行參考比較。 如果您想要比較字串值，請將運算式的左邊轉換為 `type`。  
  
 下列範例會產生 CS0252：  
  
```  
// CS0252.cs // compile with: /W:2 using System; class MyClass { public static void Main() { string s = "11"; object o = s + s; bool b = o == s;   // CS0252 // try the following line instead // bool b = (string)o == s; } }  
```