---
title: "omp_get_num_threads |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_num_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_get_num_threads OpenMP function
ms.assetid: e7c3cea1-44ac-435d-866e-2b7bc477e807
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e89c922d0382a3f795f061f61cd6bbee0fc35f53
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetnumthreads"></a>omp_get_num_threads
在平行區域傳回執行緒的數目。  
  
## <a name="syntax"></a>語法  
  
```  
int omp_get_num_threads( );  
```  
  
## <a name="remarks"></a>備註  
 如需詳細資訊，請參閱[3.1.2 omp_get_num_threads 函式](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md)。  
  
## <a name="example"></a>範例  
  
```  
// omp_get_num_threads.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()  
{  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_num_threads( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_num_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_num_threads( ));  
  
    #pragma omp parallel num_threads(3)  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_num_threads( ));  
        }  
  
    printf_s("%d\n", omp_get_num_threads( ));  
}  
```  
  
```Output  
1  
4  
1  
3  
1  
```  
  
## <a name="see-also"></a>請參閱  
 [函式](../../../parallel/openmp/reference/openmp-functions.md)