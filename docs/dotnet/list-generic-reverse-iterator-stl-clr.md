---
title: "list::generic_reverse_iterator (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::generic_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_reverse_iterator 成員 [STL/CLR]"
ms.assetid: 63435f10-5d2b-43fa-8d7a-7c5c4daf55ad
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::generic_reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

反向迭代器的型別，適合與容器的泛型介面一起使用。  
  
## 語法  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseBidirectionalIterator<generic_value> generic_reverse_iterator;  
```  
  
## 備註  
 描述泛型反向迭代器的型別，其適合與此樣本容器類別的泛型介面一起使用。  
  
## 範例  
  
```  
// cliext_list_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
 **a b c**  
 **a c c**   
## 需求  
 **標頭 ：** \<cliext\/list\>  
  
 **命名空間：** cliext  
  
## 請參閱  
 [list](../dotnet/list-stl-clr.md)   
 [list::generic\_container](../dotnet/list-generic-container-stl-clr.md)   
 [list::generic\_iterator](../dotnet/list-generic-iterator-stl-clr.md)