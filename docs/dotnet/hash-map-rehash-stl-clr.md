---
title: "hash_map::rehash (STL/CLR) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_map::rehash
dev_langs: C++
helpviewer_keywords: rehash member [STL/CLR]
ms.assetid: e894157c-4e31-4fbf-8020-b90f236da3e7
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 15c0bfbf6b35092858eb10516808dae843b60bdd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="hashmaprehash-stlclr"></a>hash_map::rehash (STL/CLR)
重建雜湊資料表。  
  
## <a name="syntax"></a>語法  
  
```  
void rehash();  
```  
  
## <a name="remarks"></a>備註  
 成員函式會重建雜湊表，如此可確保[hash_map::load_factor (STL/CLR)](../dotnet/hash-map-load-factor-stl-clr.md) `() <=` [hash_map::max_load_factor (STL/CLR)](../dotnet/hash-map-max-load-factor-stl-clr.md)。 否則，雜湊表的大小會增加只有在必要時插入後。 （它永遠不會自動減少大小。）您可以使用它來調整的雜湊資料表大小。  
  
## <a name="example"></a>範例  
  
```  
// cliext_hash_map_rehash.cpp   
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
  
```Output  
 [a 1] [b 2] [c 3]  
bucket_count() = 16  
load_factor() = 0.1875  
max_load_factor() = 4  
  
bucket_count() = 16  
load_factor() = 0.1875  
max_load_factor() = 0.25  
  
bucket_count() = 128  
load_factor() = 0.0234375  
max_load_factor() = 0.25  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/hash_map >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::bucket_count (STL/CLR)](../dotnet/hash-map-bucket-count-stl-clr.md)   
 [hash_map::load_factor (STL/CLR)](../dotnet/hash-map-load-factor-stl-clr.md)   
 [hash_map::max_load_factor (STL/CLR)](../dotnet/hash-map-max-load-factor-stl-clr.md)