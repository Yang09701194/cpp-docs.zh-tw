---
title: "編譯器錯誤 C2633 | Microsoft Docs"
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
  - "C2633"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2633"
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器錯誤 C2633
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'inline' 是建構函式唯一的合法儲存類別  
  
 建構函式宣告為儲存類別 \(Storage Class\) 而不是內嵌 \(Inline\)。  
  
 下列範例會產生 C2633：  
  
```  
// C2633.cpp  
// compile with: /c  
class C {  
   extern C();   // C2633, not inline  
   inline C();   // OK  
};  
```