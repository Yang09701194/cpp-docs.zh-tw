---
title: 編譯器錯誤 C2582 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2582
dev_langs:
- C++
helpviewer_keywords:
- C2582
ms.assetid: ee1b9378-8bcd-4792-b87e-6d7a466d29ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc8a926297f9b0762c629f031da6e12cbe528e87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2582"></a>編譯器錯誤 C2582
'function' 函式是在 'type' 中無法使用  
  
 嘗試指派物件，但是沒有指派運算子。  
  
 下列範例會產生 C2582:  
  
```  
// C2582.cpp  
// compile with: /clr  
using namespace System;  
  
struct N {};  
ref struct O {};  
ref struct R {  
   property O prop;   // C2582  
   property O ^ prop2;   // OK  
};  
  
int main() {  
   String ^ st1 = gcnew String("");  
   ^st1 = gcnew String("");   // C2582  
   st1 = "xxx";   // OK  
}  
```