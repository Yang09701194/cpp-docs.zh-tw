---
title: "omp_nest_lock_t | Microsoft Docs"
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
  - "omp_nest_lock_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_nest_lock_t OpenMP data type"
ms.assetid: fceac9fb-96d2-42b0-af19-c9b078380618
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_nest_lock_t
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

保留鎖定的資訊將下列媒體的類型： 是否鎖定可供使用，以及執行緒的識別所擁有的鎖定及巢狀的計數。  
  
 下列函式使用 **omp\_nest\_lock\_t**：  
  
-   [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)  
  
-   [omp\_destroy\_nest\_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)  
  
-   [omp\_set\_nest\_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)  
  
-   [omp\_unset\_nest\_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)  
  
-   [omp\_test\_nest\_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)  
  
 如需詳細資訊，請參閱 [3.2 Lock Functions](../../../parallel/openmp/3-2-lock-functions.md)。  
  
## 範例  
 請參閱[omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)的使用範例，  **omp\_nest\_lock\_t**。  
  
## 請參閱  
 [Data Types](../../../parallel/openmp/reference/openmp-data-types.md)