---
title: omp_get_max_threads |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_max_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_get_max_threads OpenMP function
ms.assetid: f47c3725-3e40-469f-8bc8-a1e47f264cc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 303e037d3fbeaf1958918c2ac78346bdcf01cf2a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695833"
---
# <a name="ompgetmaxthreads"></a>omp_get_max_threads
傳回一個整數，等於或大於此數目，就可以使用，如果沒有在平行區域的執行緒數目[num_threads](../../../parallel/openmp/reference/num-threads.md)在該點定義在程式碼中。  
  
## <a name="syntax"></a>語法  
  
```  
int omp_get_max_threads( )  
```  
  
## <a name="remarks"></a>備註  
 如需詳細資訊，請參閱[3.1.3 omp_get_max_threads 函式](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)。  
  
## <a name="example"></a>範例  
  
```  
// omp_get_max_threads.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_num_threads(8);  
    printf_s("%d\n", omp_get_max_threads( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_max_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_max_threads( ));  
  
    #pragma omp parallel num_threads(3)  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_max_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_max_threads( ));  
}  
```  
  
```Output  
8  
8  
8  
8  
8  
```  
  
## <a name="see-also"></a>另請參閱  
 [函式](../../../parallel/openmp/reference/openmp-functions.md)