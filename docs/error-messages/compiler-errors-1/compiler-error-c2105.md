---
title: "編譯器錯誤 C2105 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2105
dev_langs:
- C++
helpviewer_keywords:
- C2105
ms.assetid: 19b7f7bc-a9da-4d23-8193-005b6d09274f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a660d15f2e545a8fe18222eb46237ed7819c24c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2105"></a>編譯器錯誤 C2105
'operator' 需要左值  
  
 運算子必須有值 （l-value） 作為運算元。  
  
 下列範例會產生 C2105:  
  
```  
// C2105.cpp  
int main() {  
   unsigned char * p1 = 0;  
   unsigned int * p2 = (unsigned int *)p1;  
   p2++;  
  
   unsigned int * p = 0;  
   p++;   // ok  
  
   p2 = (unsigned int *)p1;  
   ((unsigned int *)p1)++;   // C2105  
}  
```  
  
 下列範例會產生 C2105:  
  
```  
// C2105b.cpp  
int main() {  
   int a[10] = {0};  
   int b[10] = {0};  
   ++(a , b);   // C2105  
  
   // OK  
   ++(a[0] , b[0]);  
   ++a[0];  
}  
```