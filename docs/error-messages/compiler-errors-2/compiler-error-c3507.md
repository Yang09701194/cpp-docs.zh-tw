---
title: "編譯器錯誤 C3507 | Microsoft Docs"
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
  - "C3507"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3507"
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 編譯器錯誤 C3507
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ProgID 可以有不超過 39 個以上的字元  'id'；不包含任何 '.' 以外的任何標點符號；也不能以數字為開頭  
  
 [progid](../../windows/progid.md) 屬性在可接受的值上有限制。  
  
 下列範例會產生 C3507：  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```