---
title: 主要 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- master
dev_langs:
- C++
helpviewer_keywords:
- master OpenMP directive
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df1cb8daf83f456c551f5b47646dce640e21c804
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686863"
---
# <a name="master"></a>主要
指定只有主要 threadshould 執行的程式 > 一節。  
  
## <a name="syntax"></a>語法  
  
```  
#pragma omp master  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>備註  
 **主要**指示詞可支援不含 OpenMP 子句。  
  
 [單一](../../../parallel/openmp/reference/single.md)指示詞可讓您指定一段程式碼，應該會在單一執行緒，而不一定是主要的執行緒上執行。  
  
 如需詳細資訊，請參閱[2.6.1 master 建構](../../../parallel/openmp/2-6-1-master-construct.md)。  
  
## <a name="example"></a>範例  
  
```  
// omp_master.cpp  
// compile with: /openmp   
#include <omp.h>  
#include <stdio.h>  
  
int main( )   
{  
    int a[5], i;  
  
    #pragma omp parallel  
    {  
        // Perform some computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] = i * i;  
  
        // Print intermediate results.  
        #pragma omp master  
            for (i = 0; i < 5; i++)  
                printf_s("a[%d] = %d\n", i, a[i]);  
  
        // Wait.  
        #pragma omp barrier  
  
        // Continue with the computation.  
        #pragma omp for  
        for (i = 0; i < 5; i++)  
            a[i] += i;  
    }  
}  
```  
  
```Output  
a[0] = 0  
a[1] = 1  
a[2] = 4  
a[3] = 9  
a[4] = 16  
```  
  
## <a name="see-also"></a>另請參閱  
 [指示詞](../../../parallel/openmp/reference/openmp-directives.md)