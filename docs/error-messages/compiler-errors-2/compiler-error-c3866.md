---
title: "編譯器錯誤 C3866 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3866"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3866"
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 編譯器錯誤 C3866
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

函式呼叫遺漏引數清單  
  
 在非靜態成員函式中，解構函式 \(Destructor\) 或完成項呼叫沒有引數清單。  
  
 下列範例會產生 C3866：  
  
```  
// C3866.cpp  
// compile with: /c  
class C {  
   ~C();  
   void f() {  
      this->~C;   // C3866  
      this->~C();   // OK  
   }  
};  
```