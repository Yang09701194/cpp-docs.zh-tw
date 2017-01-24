---
title: "編譯器錯誤 C2289 | Microsoft Docs"
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
  - "C2289"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2289"
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器錯誤 C2289
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

相同類型的限定詞已經使用多次  
  
 類型宣告或定義使用類型限定詞 \(`const`、`volatile`、`signed` 或 `unsigned`\) 多次，導致 ANSI 相容性發生錯誤 \(**\/Za**\)。  
  
 下列範例會產生 C2286：  
  
```  
// C2289.cpp // compile with: /Za /c volatile volatile int i;   // C2289 volatile int j;   // OK  
```