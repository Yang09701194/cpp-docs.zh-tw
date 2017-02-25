---
title: "編譯器錯誤 C2292 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2292"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2292"
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 編譯器錯誤 C2292
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 最佳的繼承表示: 已經宣告 'representation1'，但需要 'representation2'  
  
 使用[\/vmb](../../build/reference/vmb-vmg-representation-method.md) \(「永遠最佳狀況」表示\) 編譯下列程式碼將導致 C2292。  
  
```  
// C2292.cpp  
// compile with: /vmb  
class __single_inheritance X;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2292, X uses multiple inheritance  
```