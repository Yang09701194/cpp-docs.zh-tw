---
title: "auto_handle::operator auto_handle |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr.auto_handle.operator auto_handle
- operator auto_handle
- msclr::auto_handle::operator auto_handle
- auto_handle.operator auto_handle
- auto_handle::operator auto_handle
dev_langs:
- C++
helpviewer_keywords:
- operator auto_handle
ms.assetid: 2f8b35d1-2783-4d91-b6fb-eae551270fb8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 70f0cf35b1284bfba67f68ee84fe2b5687a4e8c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="autohandleoperator-autohandle"></a>auto_handle::operator auto_handle
型別轉型運算子之間`auto_handle`和相容的類型。  
  
## <a name="syntax"></a>語法  
  
```  
template<typename _other_type>  
operator auto_handle<_other_type>();  
```  
  
## <a name="return-value"></a>傳回值  
 目前`auto_handle`轉型為`auto_handle<_other_type>`。  
  
## <a name="example"></a>範例  
  
```  
// msl_auto_handle_op_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:  
   ClassB( String ^ s) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main() {  
   auto_handle<ClassB> b = gcnew ClassB("first");  
   b->PrintHello();  
   auto_handle<ClassA> a = (auto_handle<ClassA>)b;  
   a->PrintHello();  
}  
```  
  
```Output  
Hello from first B!  
Hello from first A!  
```  
  
## <a name="requirements"></a>需求  
 **標頭檔** \<msclr\auto_handle.h >  
  
 **命名空間**msclr  
  
## <a name="see-also"></a>請參閱  
 [auto_handle 成員](../dotnet/auto-handle-members.md)