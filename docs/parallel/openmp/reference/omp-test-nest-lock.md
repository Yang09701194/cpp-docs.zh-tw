---
title: "omp_test_nest_lock | Microsoft Docs"
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
  - "omp_test_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_test_nest_lock OpenMP function"
ms.assetid: 4c909bbe-80e0-4100-aca6-d415d7dc5294
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_test_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

嘗試設定 nestable 的鎖定，但不會封鎖執行緒的執行。  
  
## 語法  
  
```  
int omp_test_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## 備註  
 其中，  
  
 `lock`  
 型別的變數[omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) ，初始化時[omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)。  
  
## 備註  
 如需詳細資訊，請參閱 [3.2.5 omp\_test\_lock and omp\_test\_nest\_lock Functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)。  
  
## 範例  
  
```  
// omp_test_nest_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_nest_lock_t nestable_lock;      
  
int main() {  
   omp_init_nest_lock(&nestable_lock);  
  
   #pragma omp parallel num_threads(4)  
   {  
      int tid = omp_get_thread_num();  
      while (!omp_test_nest_lock(&nestable_lock))  
         printf_s("Thread %d - failed to acquire nestable_lock\n",  
                tid);  
  
      printf_s("Thread %d - acquired nestable_lock\n", tid);  
  
      if (omp_test_nest_lock(&nestable_lock)) {  
         printf_s("Thread %d - acquired nestable_lock again\n",  
                tid);  
         printf_s("Thread %d - released nestable_lock\n",   
                tid);  
         omp_unset_nest_lock(&nestable_lock);  
      }  
  
      printf_s("Thread %d - released nestable_lock\n", tid);  
      omp_unset_nest_lock(&nestable_lock);  
   }  
  
   omp_destroy_nest_lock(&nestable_lock);  
}  
```  
  
  **取得執行緒 1\-nestable\_lock**  
**執行緒 0\-無法取得 nestable\_lock**  
**一次取得執行緒 1\-nestable\_lock**  
**執行緒 0\-無法取得 nestable\_lock**  
**釋放執行緒 1\-nestable\_lock**  
**執行緒 0\-無法取得 nestable\_lock**  
**釋放執行緒 1\-nestable\_lock**  
**執行緒 0\-無法取得 nestable\_lock**  
**取得執行緒 3\-nestable\_lock**  
**執行緒 0\-無法取得 nestable\_lock**  
**一次取得執行緒 3\-nestable\_lock**  
**執行緒 0\-無法取得 nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**釋放執行緒 3\-nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**釋放執行緒 3\-nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**取得執行緒 0\-nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**一次取得執行緒 0\-nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**釋放執行緒 0\-nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**釋放執行緒 0\-nestable\_lock**  
**執行緒 2\-無法取得 nestable\_lock**  
**取得執行緒 2\-nestable\_lock**  
**一次取得執行緒 2\-nestable\_lock**  
**釋放執行緒 2\-nestable\_lock**  
**釋放執行緒 2\-nestable\_lock**   
## 請參閱  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)