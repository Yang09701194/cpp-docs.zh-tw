---
title: 'multiset:: clear (STL/CLR) |Microsoft 文件'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 63c21716-fa08-47b9-b457-0b76052c5079
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d86e3a45283ee59abb6de22931795d9f28b9260
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="multisetclear-stlclr"></a>multiset::clear (STL/CLR)
移除所有項目。  
  
## <a name="syntax"></a>語法  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>備註  
 成員函式可有效地呼叫[multiset:: erase (STL/CLR)](../dotnet/multiset-erase-stl-clr.md) `(` [multiset:: begin (STL/CLR)](../dotnet/multiset-begin-stl-clr.md) `(),` [multiset:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`())`. 您可以使用它來確定受控制的序列是空白。  
  
## <a name="example"></a>範例  
  
```  
// cliext_multiset_clear.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/set >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [多重集 (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::erase (STL/CLR)](../dotnet/multiset-erase-stl-clr.md)