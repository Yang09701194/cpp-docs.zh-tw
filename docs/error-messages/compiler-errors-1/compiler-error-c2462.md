---
title: "編譯器錯誤 C2462 | Microsoft Docs"
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
  - "C2462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2462"
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器錯誤 C2462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 無法在 'new\-expression' 中定義型別  
  
 您不能在 `new` 運算子的運算元欄位中定義型別。  將型別定義放在其他的陳述式內。  
  
 下列範例會產生 C2462：  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```