---
title: 'hash_multimap:: lower_bound (STL/CLR) |Microsoft 文件'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::lower_bound
dev_langs:
- C++
helpviewer_keywords:
- lower_bound member [STL/CLR]
ms.assetid: c61091ef-8364-4447-bdd2-a402cbc05f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2954bd890e7e274a9243b1c1405b67c1ea2887be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimaplowerbound-stlclr"></a>hash_multimap::lower_bound (STL/CLR)
尋找符合指定之索引鍵的範圍開頭。  
  
## <a name="syntax"></a>語法  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>參數  
 key  
 要搜尋的索引鍵值。  
  
## <a name="remarks"></a>備註  
 成員函式判斷第一個項目`X`雜湊至相同的值區為受控制序列中`key`且具有對等順序，以`key`。 如果沒有這類元素存在，它會傳回[hash_multimap:: end (STL/CLR)](../dotnet/hash-multimap-end-stl-clr.md)`()`; 否則它會傳回迭代器，指定`X`。 您可以使用它來尋找項目序列的開頭目前受控制序列之符合指定之索引鍵。  
  
## <a name="example"></a>範例  
  
```  
// cliext_hash_multimap_lower_bound.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Myhash_multimap::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = [a 1]  
*lower_bound(L'b') = [b 2]  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/hash_map >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap:: count (STL/CLR)](../dotnet/hash-multimap-count-stl-clr.md)   
 [hash_multimap:: equal_range (STL/CLR)](../dotnet/hash-multimap-equal-range-stl-clr.md)   
 [hash_multimap:: find (STL/CLR)](../dotnet/hash-multimap-find-stl-clr.md)   
 [hash_multimap::upper_bound (STL/CLR)](../dotnet/hash-multimap-upper-bound-stl-clr.md)