---
title: "hash_multiset:: empty (STL/CLR) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::empty
dev_langs: C++
helpviewer_keywords: empty member [STL/CLR]
ms.assetid: e1c738eb-9ac9-426b-88b0-2997c9476001
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d8a37241c0cf9e758a6863f9e7bdf24e9f7b9db3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisetempty-stlclr"></a>hash_multiset::empty (STL/CLR)
測試項目是否不存在。  
  
## <a name="syntax"></a>語法  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>備註  
 成員函式會對空的受控制序列傳回 true。 它相當於[hash_multiset:: size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md)`() == 0`。 您可以使用它來測試是否 hash_multiset 是空的。  
  
## <a name="example"></a>範例  
  
```  
// cliext_hash_multiset_empty.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/hash_set >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>請參閱  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md)