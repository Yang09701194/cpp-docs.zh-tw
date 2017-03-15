---
title: "編譯器錯誤 C2809 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2809"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2809"
ms.assetid: ce796b8e-1a8c-4074-995d-1ad09afd0e93
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 編譯器錯誤 C2809
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator' 沒有型式參數  
  
 運算子欠缺所需的參數。  
  
 下列範例會產生 C2809：  
  
```  
// C2809.cpp  
// compile with: /c  
class A{};  
int operator+ ();   // C2809  
int operator+ (A);   // OK  
```