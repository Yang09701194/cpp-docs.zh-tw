---
title: 'set:: const_reference (STL/CLR) |Microsoft 文件'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::const_reference
dev_langs:
- C++
helpviewer_keywords:
- const_reference member [STL/CLR]
ms.assetid: 25326f25-b4d3-4a92-950a-a843cdff7486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 374062f9846bd4d2bad1fc201ade788c0f58381e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="setconstreference-stlclr"></a>set::const_reference (STL/CLR)
項目的常數參考類型。  
  
## <a name="syntax"></a>語法  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>備註  
 此類型描述項目的常數參考。  
  
## <a name="example"></a>範例  
  
```  
// cliext_set_const_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Myset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        Myset::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/set >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set:: reference (STL/CLR)](../dotnet/set-reference-stl-clr.md)   
 [set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)