---
title: "編譯器錯誤 C2903 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2903"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2903"
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 編譯器錯誤 C2903
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 符號不是類別樣板，也不是函式樣板  
  
 程式碼嘗試明確具現化非樣板的某個項目。  
  
 下列範例會產生 C2903：  
  
```  
// C2903.cpp // compile with: /c namespace N { template<class T> class X {}; class Y {}; } void g() { N::template Y y;   // C2903 N::X<N::Y> y;   // OK }  
```  
  
 使用泛型時，也會發生 C2903：  
  
```  
// C2903b.cpp // compile with: /clr /c namespace N { class Y {}; generic<class T> ref class Z {}; } void f() { N::generic Y y;   // C2903 N:: generic Z<int>^ z;   // OK }  
```