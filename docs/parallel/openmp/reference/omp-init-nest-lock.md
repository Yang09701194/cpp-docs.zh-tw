---
title: "omp_init_nest_lock |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_init_nest_lock
dev_langs: C++
helpviewer_keywords: omp_init_nest_lock OpenMP function
ms.assetid: cf749ec5-de78-4186-9588-ac7c42b02463
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e137206b794344cc466b5b746e04235bd2fbf73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="ompinitnestlock"></a>omp_init_nest_lock
初始化的鎖定。  
  
## <a name="syntax"></a>語法  
  
```  
void omp_init_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>備註  
 其中：  
  
 `lock`  
 類型的變數[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)。  
  
## <a name="remarks"></a>備註  
 初始的巢狀計數為零。  
  
 如需詳細資訊，請參閱[3.2.1 omp_init_lock 和 omp_init_nest_lock 函式](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)。  
  
## <a name="example"></a>範例  
  
```  
// omp_init_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t my_lock;  
  
void Test() {  
   int tid = omp_get_thread_num( );  
   omp_set_nest_lock(&my_lock);  
   printf_s("Thread %d - starting nested locked region\n", tid);  
   printf_s("Thread %d - ending nested locked region\n", tid);  
   omp_unset_nest_lock(&my_lock);  
}  
  
int main() {  
   omp_init_nest_lock(&my_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int i, j;  
  
      for (i = 0; i < 5; ++i) {  
         omp_set_nest_lock(&my_lock);  
            if (i % 3)   
               Test();  
            omp_unset_nest_lock(&my_lock);  
        }  
    }  
  
    omp_destroy_nest_lock(&my_lock);  
}  
```  
  
```Output  
Thread 0 - starting nested locked region  
Thread 0 - ending nested locked region  
Thread 0 - starting nested locked region  
Thread 0 - ending nested locked region  
Thread 3 - starting nested locked region  
Thread 3 - ending nested locked region  
Thread 3 - starting nested locked region  
Thread 3 - ending nested locked region  
Thread 3 - starting nested locked region  
Thread 3 - ending nested locked region  
Thread 2 - starting nested locked region  
Thread 2 - ending nested locked region  
Thread 2 - starting nested locked region  
Thread 2 - ending nested locked region  
Thread 2 - starting nested locked region  
Thread 2 - ending nested locked region  
Thread 1 - starting nested locked region  
Thread 1 - ending nested locked region  
Thread 1 - starting nested locked region  
Thread 1 - ending nested locked region  
Thread 1 - starting nested locked region  
Thread 1 - ending nested locked region  
Thread 0 - starting nested locked region  
Thread 0 - ending nested locked region  
```  
  
## <a name="see-also"></a>請參閱  
 [函式](../../../parallel/openmp/reference/openmp-functions.md)