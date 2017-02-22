---
title: "hash_map::load_factor (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::load_factor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "load_factor 成員 [STL/CLR]"
ms.assetid: e3a29b1f-ea20-4153-87b0-3935044d4d7a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# hash_map::load_factor (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

計數平均項目每個 Bucket。  
  
## 語法  
  
```  
float load_factor();  
```  
  
## 備註  
 成員函式傳回 `(float)`[hash\_map::size](../dotnet/hash-map-size-stl-clr.md)`() /`[hash\_map::bucket\_count](../dotnet/hash-map-bucket-count-stl-clr.md)`()`。  您會用它來判斷平均 Bucket 大小。  
  
## 範例  
  
```  
// cliext_hash_map_load_factor.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1 = gcnew Myhash_map;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect current parameters   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.25f);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    System::Console::WriteLine();   
  
// rehash and redisplay   
    c1.rehash(100);   
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());   
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());   
    System::Console::WriteLine("max_load_factor() = {0}",   
        c1.max_load_factor());   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**bucket\_count \(\) \= 16**  
**load\_factor \(\) \= 0.1875**  
**max\_load\_factor \(\) \= 4**  
**bucket\_count \(\) \= 16**  
**load\_factor \(\) \= 0.1875**  
**max\_load\_factor \(\) \= 0.25**  
**bucket\_count \(\) \= 128**  
**load\_factor \(\) \= 0.0234375**  
**max\_load\_factor \(\) \= 0.25**   
## 需求  
 **標題:** \<cliext\/hash\_map\>  
  
 **命名空間:** cliext  
  
## 請參閱  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::bucket\_count](../dotnet/hash-map-bucket-count-stl-clr.md)   
 [hash\_map::max\_load\_factor](../dotnet/hash-map-max-load-factor-stl-clr.md)