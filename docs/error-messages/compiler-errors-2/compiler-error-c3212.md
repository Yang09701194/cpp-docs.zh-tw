---
title: "編譯器錯誤 C3212 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3212"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3212"
ms.assetid: 9e271bb6-a51f-4b96-b26b-9f4ca28fca0a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 編譯器錯誤 C3212
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specialization' : 樣板成員的明確特製化必須是明確特製化的成員  
  
 明確特製化的格式不正確。  
  
 下列範例會產生 C3212：  
  
```  
// C3212.cpp // compile with: /LD template <class T> struct S { template <class T1> struct S1; }; template <class T>   // C3212 template <> struct S<T>::S1<int> {}; /* // try the following instead template <> template <> struct S<int>::S1<int> {}; */ /* // or, the following template <> struct S<int> { template <class T1> struct S1; }; template <> struct S<int>::S1<int> { }; */  
```