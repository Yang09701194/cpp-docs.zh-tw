---
title: 編譯器警告 （層級 1） C4020 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4020
dev_langs:
- C++
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb7926e22802178ff3cbcb710fbc9b74e7138f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4020"></a>編譯器警告 （層級 1） C4020
'function': 實質參數太多  
  
 函式呼叫中的實際參數數目超過函式原型或定義中正式參數數目。 編譯器會傳遞額外實質參數根據函式的呼叫慣例。  
  
 下列範例會產生 C4020:  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 可能的解決方式：  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```