---
title: "list:: value_type (STL/CLR) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::value_type
dev_langs: C++
helpviewer_keywords: value_type member [STL/CLR]
ms.assetid: 7013f92e-8ceb-4c99-bb44-6ba13b0d3ef3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 657daeeefce02c312a1ed4811466fb9dddaa9a4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="listvaluetype-stlclr"></a>list::value_type (STL/CLR)
元素的類型。  
  
## <a name="syntax"></a>語法  
  
```  
typedef Value value_type;  
```  
  
## <a name="remarks"></a>備註  
 此類型是範本參數 `Value`的同義字。  
  
## <a name="example"></a>範例  
  
```  
// cliext_list_value_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::list<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/清單 >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>請參閱  
 [清單 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list:: const_reference (STL/CLR)](../dotnet/list-const-reference-stl-clr.md)   
 [list::reference (STL/CLR)](../dotnet/list-reference-stl-clr.md)