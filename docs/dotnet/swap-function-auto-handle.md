---
title: "swap 函式 (auto_handle) |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::swap
- msclr.swap
dev_langs: C++
helpviewer_keywords: swap function
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c400579603ce3385e6b4114c8c9996cab2849619
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="swap-function-autohandle"></a>swap 函式 (auto_handle)
交換物件之間一個`auto_handle`和另一個。  
  
## <a name="syntax"></a>語法  
  
```  
template<typename _element_type>  
void swap(  
   auto_handle<_element_type> % _left,  
   auto_handle<_element_type> % _right  
);  
```  
  
#### <a name="parameters"></a>參數  
 `_left`  
 `auto_handle`。  
  
 `_right`  
 另一個`auto_handle`。  
  
## <a name="example"></a>範例  
  
```  
// msl_swap_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   swap( s1, s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
```Output  
s1 = 'string one', s2 = 'string two'  
s1 = 'string two', s2 = 'string one'  
```  
  
## <a name="requirements"></a>需求  
 **標頭檔** \<msclr\auto_handle.h >  
  
 **命名空間**msclr  
  
## <a name="see-also"></a>請參閱  
 [auto_handle](../dotnet/auto-handle.md)   
 [auto_handle::swap](../dotnet/auto-handle-swap.md)