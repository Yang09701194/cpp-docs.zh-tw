---
title: 使用的重要指示詞 A.5 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1a41e9664faaca24b6708c737a044828eb460bd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2018
---
# <a name="a5---using-the-critical-directive"></a>A.5 使用 critical 指示詞
下列範例包含數個`critical`指示詞 ([區段 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md)第 18 頁上)。 此範例說明工作會清除佇列並處理過的佇列模型。 若要防範取消佇列相同的工作的多個執行緒，清除佇列作業必須在`critical`> 一節。 在此範例中的兩個佇列無關，因為它們由保護`critical`具有不同的名稱，指示詞*xaxis*和*y 軸*。  
  
```  
#pragma omp parallel shared(x, y) private(x_next, y_next)  
{  
    #pragma omp critical ( xaxis )  
        x_next = dequeue(x);  
    work(x_next);  
    #pragma omp critical ( yaxis )  
        y_next = dequeue(y);  
    work(y_next);  
}  
```