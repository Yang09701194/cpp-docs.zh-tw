---
title: "編譯器錯誤 C3219 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3219"
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 編譯器錯誤 C3219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param': 泛型參數不可受到多重非介面的條件約束: 'class'  
  
 不可以透過兩個以上的 Managed 類別來限制泛型參數。  
  
 下列範例會產生 C3219：  
  
```  
// C3219.cpp // compile with: /clr ref class A {}; ref class B {}; generic <class T> where T : A, B ref class E {};   // C3219  
```  
  
 下列範例示範可能的解決方式：  
  
```  
// C3219b.cpp // compile with: /clr /c ref class A {}; interface struct C {}; generic <class T> where T : A ref class E {};  
```