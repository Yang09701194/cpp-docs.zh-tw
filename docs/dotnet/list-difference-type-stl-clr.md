---
title: "list::difference_type (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::difference_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "difference_type 成員 [STL/CLR]"
ms.assetid: 0044d53b-47d8-4c96-b996-b5492c0679c3
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::difference_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

兩個項目之間的帶正負號距離的類型。  
  
## 語法  
  
```  
typedef int difference_type;  
```  
  
## 備註  
 此型別描述已簽署的項目計數。  
  
## 範例  
  
```  
// cliext_list_difference_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::list<wchar_t>::difference_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **a b c**  
**end\(\)\-begin\(\) \= 3**  
**begin\(\)\-end\(\) \= \-3**   
## 需求  
 **標頭 ：** \<cliext\/list\>  
  
 **命名空間：** cliext  
  
## 請參閱  
 [list](../dotnet/list-stl-clr.md)   
 [list::size\_type](../dotnet/list-size-type-stl-clr.md)