---
title: "編譯器錯誤 C3004 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3004
dev_langs: C++
helpviewer_keywords: C3004
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6468ecdf001789a487658d80d50bc843e2df8e96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3004"></a>編譯器錯誤 C3004
'clause' : 子句對 OpenMP 'directive' 指示詞無效  
  
 OpenMP 子句用在未啟用的指示詞上。  
  
 下列範例會產生 C3004：  
  
```  
// C3004.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
  
   // Shared clause not allowed for 'single' directive.  
   #pragma omp single shared(x, y)   // C3004  
  
   x = y;  
}  
```