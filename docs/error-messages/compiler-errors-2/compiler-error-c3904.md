---
title: "編譯器錯誤 C3904 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3904"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3904"
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 編譯器錯誤 C3904
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property\_accessor' : 必須指定參數數目  
  
 根據屬性大小，檢查 `get` 和 `set` 方法中的參數數目。  
  
-   `get` 方法的參數數目必須等於屬性大小的數目，或是未進行索引的屬性則為零。  
  
-   `set` 方法的參數數目必須比屬性大小的數目多一個。  
  
 如需詳細資訊，請參閱[屬性](../../windows/property-cpp-component-extensions.md)。  
  
## 範例  
 下列範例會產生 C3904。  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## 範例  
 下列範例會產生 C3904。  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```