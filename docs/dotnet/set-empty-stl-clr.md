---
title: "set:: empty (STL/CLR) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::empty
dev_langs: C++
helpviewer_keywords: empty member [STL/CLR]
ms.assetid: af10279f-e9e8-4599-b59b-5b8d92b619eb
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a19b2b3536ef63c30bd19ee1aa7876de2b1c64a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="setempty-stlclr"></a>set::empty (STL/CLR)
測試項目是否不存在。  
  
## <a name="syntax"></a>語法  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>備註  
 成員函式會對空的受控制序列傳回 true。 它相當於[set:: size (STL/CLR)](../dotnet/set-size-stl-clr.md)`() == 0`。 您可以使用它來測試集合是否為空白。  
  
## <a name="example"></a>範例  
  
```  
// cliext_set_empty.cpp   
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
 **標頭：** \<cliext/set >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)