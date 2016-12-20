---
title: "omp_test_lock | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_test_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_lock OpenMP function"
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_test_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

嘗試設定鎖定，但不會封鎖執行緒的執行。  
  
## 語法  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
## 備註  
 其中，  
  
 `lock`  
 型別的變數[omp\_lock\_t](../../../parallel/openmp/reference/omp-lock-t.md) ，初始化時[omp\_init\_lock](../../../parallel/openmp/reference/omp-init-lock.md)。  
  
## 備註  
 如需詳細資訊，請參閱 [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)。  
  
## 範例  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
  **取得執行緒 1\-simple\_lock**  
**釋放執行緒 1\-simple\_lock**  
**執行緒 0\-無法取得 simple\_lock**  
**執行緒 3\-無法取得 simple\_lock**  
**執行緒 0\-無法取得 simple\_lock**  
**執行緒 3\-無法取得 simple\_lock**  
**取得執行緒 2\-simple\_lock**  
**執行緒 0\-無法取得 simple\_lock**  
**執行緒 3\-無法取得 simple\_lock**  
**執行緒 0\-無法取得 simple\_lock**  
**執行緒 3\-無法取得 simple\_lock**  
**釋放執行緒 2\-simple\_lock**  
**執行緒 0\-無法取得 simple\_lock**  
**執行緒 3\-無法取得 simple\_lock**  
**取得執行緒 0\-simple\_lock**  
**執行緒 3\-無法取得 simple\_lock**  
**釋放執行緒 0\-simple\_lock**  
**執行緒 3\-無法取得 simple\_lock**  
**取得執行緒 3\-simple\_lock**  
**釋放執行緒 3\-simple\_lock**   
## 請參閱  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)