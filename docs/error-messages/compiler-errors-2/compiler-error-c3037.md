---
title: "編譯器錯誤 C3037 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3037
dev_langs: C++
helpviewer_keywords: C3037
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 326d1642dab479501031d182cd916db8e4eb30cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3037"></a>編譯器錯誤 C3037
'var': 'reduction' 子句中的變數在封入內容中必須為共用  
  
 [reduction](../../parallel/openmp/reference/reduction.md) 子句中指定的變數，對內容中的每個執行緒而言可能都不是私用。  
  
 下列範例會產生 C3037：  
  
```  
// C3037.cpp  
// compile with: /openmp /c  
int g_i;  
  
int main() {  
   int i;  
  
   #pragma omp parallel private(g_i)  
   // try the following line instead  
   // #pragma omp parallel   
   {  
      #pragma omp for reduction(+:g_i)   // C3037  
      for (i = 0 ; i < 10 ; ++i) {  
         g_i += i;  
      }  
   }  
}  
```