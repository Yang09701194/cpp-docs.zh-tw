---
title: 'vector:: reference (STL/CLR) |Microsoft 文件'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::reference
dev_langs:
- C++
helpviewer_keywords:
- reference member [STL/CLR]
ms.assetid: 6ea0d3b0-d2e6-42c3-856c-a10f5ef7620c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 131d296942bec21d25f9d274f9f55457874ced34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168912"
---
# <a name="vectorreference-stlclr"></a>vector::reference (STL/CLR)
項目的參考類型。  
  
## <a name="syntax"></a>語法  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>備註  
 此類型描述項目的參考。  
  
## <a name="example"></a>範例  
  
```  
// cliext_vector_reference.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
  
        ref += (wchar_t)(L'A' - L'a');   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
A B C  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<向量 cliext/>  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [向量 (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector:: const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)   
 [vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)