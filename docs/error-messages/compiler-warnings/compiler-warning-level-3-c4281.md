---
title: "編譯器警告 (層級 3) C4281 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4281"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4281"
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 編譯器警告 (層級 3) C4281
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

透過型別 'type' 發生 'operator –\>' 遞迴  
  
 您的程式碼允許 **operator–\>** 呼叫其本身。  
  
 下列範例會產生 C4281：  
  
```  
// C4281.cpp  
// compile with: /W3 /WX  
struct A;  
struct B;  
struct C;  
  
struct A  
{  
   int z;  
   B& operator->();  
};  
  
struct B  
{  
   C& operator->();  
};  
  
struct C  
{  
   A& operator->();  
};  
  
void f(A p)  
{  
   int i = p->z; // C4281  
}  
```