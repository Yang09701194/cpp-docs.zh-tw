---
title: "deque:: const_reference (STL/CLR) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::deque::const_reference
dev_langs: C++
helpviewer_keywords: const_reference member [STL/CLR]
ms.assetid: daa4a3dc-cae9-46da-b62c-c2870edb120f
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 49187874965ac9f79b4f8dcbf6630c0cc9117017
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="dequeconstreference-stlclr"></a>deque::const_reference (STL/CLR)
項目的常數參考類型。  
  
## <a name="syntax"></a>語法  
  
```  
typedef value_type% const_reference;  
```  
  
## <a name="remarks"></a>備註  
 此類型描述項目的常數參考。  
  
## <a name="example"></a>範例  
  
```  
// cliext_deque_const_reference.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::deque<wchar_t>::const_reference cref = *cit;   
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
 **標頭：** \<cliext/deque >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>請參閱  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque:: reference (STL/CLR)](../dotnet/deque-reference-stl-clr.md)   
 [deque::value_type (STL/CLR)](../dotnet/deque-value-type-stl-clr.md)