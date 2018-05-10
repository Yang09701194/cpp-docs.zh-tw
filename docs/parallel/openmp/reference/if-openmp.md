---
title: 如果 (OpenMP) |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- if OpenMP clause
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2467c295c4f2724ec6d258e844f2bdaa84cfe29
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2018
---
# <a name="if-openmp"></a>if (OpenMP)
指定在平行或序列中，是否應該執行迴圈。  
  
## <a name="syntax"></a>語法  
  
```  
if(expression)  
```  
  
## <a name="remarks"></a>備註  
 其中：  
  
 `expression`  
 整數運算式，如果評估為 true （非零），會導致程式碼中以平行方式執行的平行區域。 如果運算式評估為 false （零），在平行區域中執行序列 （由單一執行緒）。  
  
## <a name="remarks"></a>備註  
 `if` 適用於下列指示詞：  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [區段](../../../parallel/openmp/reference/sections-openmp.md)  
  
 如需詳細資訊，請參閱[2.3 parallel 建構](../../../parallel/openmp/2-3-parallel-construct.md)。  
  
## <a name="example"></a>範例  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
```Output  
val = 0, serialized  
val = 2, parallelized with 2 threads  
```  
  
## <a name="see-also"></a>另請參閱  
 [子句](../../../parallel/openmp/reference/openmp-clauses.md)