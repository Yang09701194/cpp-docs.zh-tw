---
title: 標準轉換和隱含 Boxing |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxing, implicit
ms.assetid: 33f7fc7d-5674-44a2-a859-0e6a04fae519
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0540958e39f54e16ee7d158afe2845e8526a67d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163201"
---
# <a name="standard-conversions-and-implicit-boxing"></a>標準轉換和隱含 Boxing
在需要進行 Boxing 的轉換時，編譯器會選擇進行標準轉換。  
  
## <a name="example"></a>範例  
  
```  
// clr_implicit_boxing_Std_conversion.cpp  
// compile with: /clr  
int f3(int ^ i) {   // requires boxing  
   return 1;  
}  
  
int f3(char c) {   // no boxing required, standard conversion  
   return 2;  
}  
  
int main() {  
   int i = 5;  
   System::Console::WriteLine(f3(i));  
}  
```  
  
```Output  
2  
```  
  
## <a name="see-also"></a>另請參閱  
 [Boxing](../windows/boxing-cpp-component-extensions.md)