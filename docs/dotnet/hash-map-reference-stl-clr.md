---
title: 'hash_map:: reference (STL/CLR) |Microsoft 文件'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::reference
dev_langs:
- C++
helpviewer_keywords:
- reference member [STL/CLR]
ms.assetid: 4aac6eb4-0792-477d-b285-e83d9601cc99
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fcf8f67360f7f6bc2283dc88e750dc0b11fc665e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="hashmapreference-stlclr"></a>hash_map::reference (STL/CLR)
項目的參考類型。  
  
## <a name="syntax"></a>語法  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>備註  
 此類型描述項目的參考。  
  
## <a name="example"></a>範例  
  
```  
// cliext_hash_map_reference.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    Myhash_map::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Myhash_map::reference ref = *it;   
        System::Console::Write(" [{0} {1}]", ref->first, ref->second);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/hash_map >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map:: const_reference (STL/CLR)](../dotnet/hash-map-const-reference-stl-clr.md)   
 [hash_map::value_type (STL/CLR)](../dotnet/hash-map-value-type-stl-clr.md)