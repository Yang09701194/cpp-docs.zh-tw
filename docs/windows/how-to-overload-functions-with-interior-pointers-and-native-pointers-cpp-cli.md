---
title: 如何： 多載具有內部指標與原生指標的函式 (C + + /CLI) |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Functions with interior and native pointers, overloading
ms.assetid: d70df625-4aad-457c-84f5-70a0a290cc1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e3bc7e5fca6a34f9847c913e92e523b2898068f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874859"
---
# <a name="how-to-overload-functions-with-interior-pointers-and-native-pointers-ccli"></a>如何：多載具有內部指標與原生指標的函式 (C++/CLI)
函式可以多載根據參數型別是內部指標或原生指標。  
  
> [!IMPORTANT]
>  這項語言功能會受到 **/clr**編譯器選項，但不是由 **/ZW**編譯器選項。  
  
## <a name="example"></a>範例  
  
### <a name="code"></a>程式碼  
  
```  
// interior_ptr_overload.cpp  
// compile with: /clr  
using namespace System;  
  
// C++ class  
struct S {  
   int i;  
};  
  
// managed class  
ref struct G {  
   int i;  
};  
  
// can update unmanaged storage  
void f( int* pi ) {  
   *pi = 10;  
   Console::WriteLine("in f( int* pi )");  
}  
  
// can update managed storage  
void f( interior_ptr<int> pi ) {  
   *pi = 10;   
   Console::WriteLine("in f( interior_ptr<int> pi )");  
}  
  
int main() {  
   S *pS = new S;   // C++ heap  
   G ^pG = gcnew G;   // common language runtime heap  
   f( &pS->i );  
   f( &pG->i );  
};  
```  
  
### <a name="output"></a>輸出  
  
```  
in f( int* pi )  
in f( interior_ptr<int> pi )  
```  
  
## <a name="see-also"></a>另請參閱  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)