---
title: "auto_handle::swap |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_handle::swap
- auto_handle.swap
- auto_handle::swap
- msclr..auto_handle.swap
dev_langs: C++
helpviewer_keywords: auto_handle::swap
ms.assetid: 3ebf82d7-9b69-4a72-a22d-69b4f640f9b0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5b0a92773cbeae8e37cd2b2978ab51bcbfda7de1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="autohandleswap"></a>auto_handle::swap
交換與另一個物件`auto_handle`。  
  
## <a name="syntax"></a>語法  
  
```  
void swap(  
   auto_handle<_element_type> % _right  
);  
```  
  
#### <a name="parameters"></a>參數  
 `_right`  
 `auto_handle`用來交換物件。  
  
## <a name="example"></a>範例  
  
```  
// msl_auto_handle_swap.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   s1.swap( s2 );  
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
 [auto_handle 成員](../dotnet/auto-handle-members.md)   
 [swap 函式 (auto_handle)](../dotnet/swap-function-auto-handle.md)