---
title: "編譯器錯誤 CS0214 | Microsoft Docs"
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
  - "CS0214"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0214"
ms.assetid: be1ef909-a53e-485f-a79b-b1cc56cead15
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 編譯器錯誤 CS0214
指標和固定大小緩衝區只能使用於 unsafe 內容中  
  
 指標只能與 [unsafe](../Topic/unsafe%20\(C%23%20Reference\).md) 關鍵字搭配使用。 如需詳細資訊，請參閱[Unsafe 程式碼和指標](../Topic/Unsafe%20Code%20and%20Pointers%20\(C%23%20Programming%20Guide\).md)。  
  
 下列範例會產生 CS0214：  
  
```  
// CS0214.cs // compile with: /target:library /unsafe public struct S { public int a; } public class MyClass { public static void Test() { S s = new S(); S * s2 = &s;    // CS0214 s2->a = 3;      // CS0214 s.a = 0; } // OK unsafe public static void Test2() { S s = new S(); S * s2 = &s; s2->a = 3; s.a = 0; } }  
```