---
title: "編譯器錯誤 CS0746 | Microsoft Docs"
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
  - "CS0746"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0746"
ms.assetid: 36baf7f2-b092-422c-ab53-95154bfceb0a
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS0746
匿名類型成員宣告子無效。 匿名類型成員必須以成員指派、簡單名稱或成員存取加以宣告。  
  
 匿名類型必須以成員指派、簡單名稱或成員存取加以宣告。  
  
### 更正這個錯誤  
  
1.  請確定您的宣告僅使用成員指派、簡單名稱或成員存取運算式。  
  
## 範例  
 下列程式碼會在 `incorrect_1` 和 `incorrect_2` 的宣告中產生 CS0746。 下列宣告顯示兩種宣告匿名類型的正確方式。  
  
```  
// cs0746.cs public class C { public static int Main() { int i = 100; string s = "Bottles of beer."; var incorrect_1 = new { a.b = 1 }; // CS0746 var incorrect_2 = new {100, "Bottles of beer."}; // CS0746 var correct_1 = new { i, s }; //OK var correct_2 = new {num = i, message = s}; // OK return 1; } }  
  
```  
  
## 請參閱  
 [匿名類型](../Topic/Anonymous%20Types%20\(C%23%20Programming%20Guide\).md)