---
title: "編譯器警告 (層級 1) C4176 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4176"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4176"
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 編譯器警告 (層級 1) C4176
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'subcomponent': \#pragma 元件瀏覽器的未知子元件  
  
 **component** pragma 包含無效的子元件。 若要排除特定名稱的參考，您必須在名稱前面使用**參考**選項。  
  
## 範例  
  
```  
// C4176.cpp // compile with: /W1 /LD #pragma component(browser, off, i)  // C4176 #pragma component(browser, off, references, i) // ok  
```