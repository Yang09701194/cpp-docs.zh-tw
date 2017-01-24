---
title: "queue::front (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::front"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front 成員 [STL/CLR]"
ms.assetid: 9d7bb95f-5896-42f7-86fa-004a7a65cc94
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue::front (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

存取第一個項目。  
  
## 語法  
  
```  
reference front();  
```  
  
## 備註  
 成員函式傳回參考給受控制序列的第一個項目，此序列不能為空序列。  當您知道它存在，您會用它來存取第一個項目。  
  
## 範例  
  
```  
// cliext_queue_front.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**front\(\) \= a**  
 **x b c**   
## 需求  
 **標頭：** \<cliext\/queue\>  
  
 **命名空間：** cliext  
  
## 請參閱  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::back](../dotnet/queue-back-stl-clr.md)   
 [queue::back\_item](../dotnet/queue-back-item-stl-clr.md)   
 [queue::front\_item](../dotnet/queue-front-item-stl-clr.md)