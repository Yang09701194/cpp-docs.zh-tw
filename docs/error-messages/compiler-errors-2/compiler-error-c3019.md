---
title: 編譯器錯誤 C3019 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3019
dev_langs:
- C++
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 390a05af4c81104c081376d45f12f1a9cd8a91d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3019"></a>編譯器錯誤 C3019
在 OpenMP 'for' 陳述式的遞增值具有格式不正確  
  
 OpenMP 遞增一部分`for`迴圈必須使用索引變數，同時在左方和運算子的右邊。  
  
 下列範例會產生 C3019:  
  
```  
// C3019.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 1, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i = j + n)   // C3019  
      // Try the following line instead:  
      // for (i = 0; i < 10; i++)  
         j *= 2;  
   }  
}  
```