---
title: "決定使用的執行緒數目 A.15 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8b7fb8cf6218863287d582a097cb43b399cff07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15 判斷使用的執行緒數目
請考慮下列不正確的範例 (如[區段 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 頁面上):  
  
```  
np = omp_get_num_threads(); // misplaced   
#pragma omp parallel for schedule(static)  
    for (i=0; i<np; i++)  
        work(i);  
```  
  
 `omp_get_num_threads()`序列一節的程式碼，呼叫傳回 1，因此*np*一定會在上述範例中為 1 相等。 若要判斷將部署的平行區域的執行緒數目，呼叫應該會在平行區域內。  
  
 下列範例顯示如何不包括的執行緒數目的查詢重新撰寫此程式：  
  
```  
#pragma omp parallel private(i)  
{  
    i = omp_get_thread_num();  
    work(i);  
}  
```