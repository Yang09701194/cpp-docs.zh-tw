---
title: "編譯器警告 (層級 1) C4661 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4661"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4661"
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器警告 (層級 1) C4661
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 未提供明確樣板具現化 \(Explicit Template Instantiation\) 所要求的合適定義  
  
 未定義樣板類別 \(Template Class\) 的成員。  
  
## 範例  
  
```  
// C4661.cpp  
// compile with: /W1 /LD  
template<class T> class MyClass {  
public:  
   void i();   // declaration but not definition  
};  
template MyClass< int >;  // C4661  
```