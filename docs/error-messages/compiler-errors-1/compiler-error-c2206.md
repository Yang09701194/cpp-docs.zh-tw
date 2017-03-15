---
title: "編譯器錯誤 C2206 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2206"
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 編譯器錯誤 C2206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 函式定義不可以使用 typedef  
  
 `typedef` 已用來定義函式類型。  
  
 下列範例會產生 C2206：  
  
```  
// C2206.cpp typedef int functyp(); typedef int MyInt; functyp func1 {};   // C2206 int main() { MyInt i = 0;   // OK }  
```