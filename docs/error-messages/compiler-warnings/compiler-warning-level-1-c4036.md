---
title: "編譯器警告 (層級 1) C4036 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4036"
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器警告 (層級 1) C4036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

未命名的 'type' 當做實質參數  
  
 未針對結構、等位、列舉或作為實質參數的類別提供任何類型名稱。 如果您使用 [\/Zg](../../build/reference/zg-generate-function-prototypes.md) 來產生函式原型，編譯器會發出這個警告並將產生之原型中的型式參數標記為註解。  
  
 請指定類型名稱來解決這個警告。  
  
## 範例  
 下列範例會產生 C4036：  
  
```  
// C4036.c // compile with: /Zg /W1 // D9035 expected typedef struct { int i; } T; void f(T* t) {}   // C4036 // OK typedef struct MyStruct { int i; } T2; void f2(T2 * t) {}  
```