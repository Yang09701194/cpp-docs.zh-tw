---
title: 編譯器錯誤 C2783 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2783
dev_langs:
- C++
helpviewer_keywords:
- C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c16e74e8187b92778eda3392560d2f9a02e05b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234399"
---
# <a name="compiler-error-c2783"></a>編譯器錯誤 C2783
'declaration': 無法推算 'identifier' 的樣板引數  
  
 編譯器無法判斷樣板引數。 預設引數不能用來推算樣板引數。  
  
 下列範例會產生 C2783:  
  
```  
// C2783.cpp  
template<typename T1, typename T2>  
T1 f(T2) {  
   return 248;  
}  
  
int main() {  
   f(1);   // C2783  
   // try the following line instead  
   int i = f<int>(1);  
}  
```  
  
 使用泛型時，也會發生 C2783:  
  
```  
// C2783b.cpp  
// compile with: /clr  
using namespace System;  
generic<typename T1, typename T2>   
T1 gf(T2) {  
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));  
   return t1;  
}  
  
ref class MyClass{};  
  
int main() {  
   int i;  
   i = gf(9);   // C2783  
  
   // OK  
   i = gf<int>(9);  
}  
```