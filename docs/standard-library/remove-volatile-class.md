---
title: "remove_volatile 類別 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::remove_volatile"
  - "std.tr1.remove_volatile"
  - "remove_volatile"
  - "std.remove_volatile"
  - "std::remove_volatile"
  - "type_traits/std::remove_volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_volatile 類別 [TR1]"
  - "remove_volatile"
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove_volatile 類別
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

從類型建立非 volatile 類型。  
  
## 語法  
  
```  
template<class T>  
    struct remove_volatile;  
  
template<class T>  
  using remove_volatile_t = typename remove_volatile<T>::type;  
```  
  
#### 參數  
 `T`  
 要修改的類型。  
  
## 備註  
 `remove_volatile<T>` 執行個體儲存修改的類型，如果 `T1` 的格式為 `T`，類型為 `volatile T1`，否則為 `T`。  
  
## 範例  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_volatile_t<volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << " remove_volatile_t<volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **remove\_volatile\_t\<volatile int\> \=\= int**   
## 需求  
 **標頭：**\<type\_traits\>  
  
 **命名空間:** std  
  
## 請參閱  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_volatile 類別](../standard-library/add-volatile-class.md)