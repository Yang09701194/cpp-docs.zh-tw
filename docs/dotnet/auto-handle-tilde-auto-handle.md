---
title: 'auto_handle:: ~ auto_handle |Microsoft 文件'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_handle.~auto_handle
- msclr.auto_handle.~auto_handle
- auto_handle::~auto_handle
- ~auto_handle
- msclr::auto_handle::~auto_handle
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::~auto_handle
ms.assetid: e83e95a8-015b-4f27-ad63-70efb3690726
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4ba4ab13a2bd4fd16a09f91a5a382401d71ad73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102614"
---
# <a name="autohandleautohandle"></a>auto_handle::~auto_handle
`auto_handle`解構函式。  
  
## <a name="syntax"></a>語法  
  
```  
~auto_handle();  
```  
  
## <a name="remarks"></a>備註  
 解構函式也 destructs 擁有的物件。  
  
## <a name="example"></a>範例  
  
```  
// msl_auto_handle_dtor.cpp  
// compile with: /clr  
#include "msclr\auto_handle.h"  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
public:  
   ClassA() { Console::WriteLine( "ClassA constructor" ); }  
   ~ClassA() { Console::WriteLine( "ClassA destructor" ); }  
};  
  
int main()  
{  
   // create a new scope for a:  
   {  
      auto_handle<ClassA> a = gcnew ClassA;  
   }  
   // a goes out of scope here, invoking its destructor  
   // which in turns destructs the ClassA object.  
  
   Console::WriteLine( "done" );  
}  
```  
  
```Output  
ClassA constructor  
ClassA destructor  
done  
```  
  
## <a name="requirements"></a>需求  
 **標頭檔** \<msclr\auto_handle.h >  
  
 **命名空間**msclr  
  
## <a name="see-also"></a>另請參閱  
 [auto_handle 成員](../dotnet/auto-handle-members.md)   
 [auto_handle::release](../dotnet/auto-handle-release.md)   
 [auto_handle::auto_handle](../dotnet/auto-handle-auto-handle.md)