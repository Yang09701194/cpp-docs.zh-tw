---
title: 運算子 = = （組） (STL/CLR) |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair::operator==
dev_langs:
- C++
helpviewer_keywords:
- operator== member [STL/CLR]
ms.assetid: 2b4879a1-f326-4fb3-b113-bd8d457f9802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4bb070a13058e75cff7dd923a7f388f51732334e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33137825"
---
# <a name="operator-pair-stlclr"></a>operator== (pair) (STL/CLR)
配對相等比較。  
  
## <a name="syntax"></a>語法  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator==(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>參數  
 左  
 要比較的左的組。  
  
 向右  
 要比較的右組。  
  
## <a name="remarks"></a>備註  
 運算子函式會傳回`left.first ==` `right.first &&` `left.second ==` `right.second`。 使用它來測試是否`left`排序相同`right`兩組時項目所比較的項目。  
  
## <a name="example"></a>範例  
  
```  
// cliext_pair_operator_eq.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] == [x 3] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[x 3] == [x 4] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] == [x 3] is True  
[x 3] == [x 4] is False  
```  
  
## <a name="requirements"></a>需求  
 **標頭：** \<cliext/公用程式 >  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>另請參閱  
 [配對 (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [運算子 ！ = （組） (STL/CLR)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [運算子\<（組） (STL/CLR)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [運算子 > = （組） (STL/CLR)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [運算子 > （組） (STL/CLR)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator<= (pair) (STL/CLR)](../dotnet/operator-less-or-equal-pair-stl-clr.md)