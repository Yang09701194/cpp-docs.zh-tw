---
title: "queue:: container_type (STL/CLR) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::container_type
dev_langs: C++
helpviewer_keywords: container_type member [STL/CLR]
ms.assetid: 118168f9-e5ed-47e2-a4f5-26b0b56e41e1
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 115991acdf4c2a337f521c5c03e5e02458445c2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="queuecontainertype-stlclr"></a>queue::container_type (STL/CLR)
基礎容器的類型。  
  
## <a name="syntax"></a>語法  
  
```  
typedef Container value_type;  
```  
  
## <a name="remarks"></a>備註  
 此類型是範本參數 `Container`的同義字。  
  
## <a name="example"></a>範例  
  
```  
// cliext_queue_container_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Myqueue::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/佇列 >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>請參閱  
 [佇列 (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::get_container (STL/CLR)](../dotnet/queue-get-container-stl-clr.md)