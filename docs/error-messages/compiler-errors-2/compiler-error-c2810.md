---
title: "編譯器錯誤 C2810 | Microsoft Docs"
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
  - "C2810"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2810"
ms.assetid: f63e8f24-d7f6-42ac-904f-72ff49592ba6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器錯誤 C2810
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : 介面只可以繼承自另一介面  
  
 [介面](../../cpp/interface.md)只可以繼承另一介面，不能繼承類別或結構。  
  
 下列範例會產生 C2810：  
  
```  
// C2810.cpp  
#include <unknwn.h>  
class CBase1 {  
public:  
  HRESULT mf1();  
  int  m_i;  
};  
  
[object, uuid="40719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IDerived : public CBase1 {  // C2810  
// try the following line instead  
// __interface IDerived {  
   HRESULT mf2(void *a);  
};  
  
struct CBase2 {  
   HRESULT mf1(int a, char *b);  
   HRESULT mf2();  
};  
```