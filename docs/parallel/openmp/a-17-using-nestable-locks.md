---
title: "使用可巢狀鎖定 A.17 |Microsoft 文件"
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
ms.assetid: 8ef386ed-ddc4-4d40-80aa-cc39f0fb5e4b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e7bfaa0f03eec11cf4a45115c03a8553ad54fb0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="a17---using-nestable-locks"></a>A.17 使用可巢狀鎖定
下列範例 (如[第 3.2 節](../../parallel/openmp/3-2-lock-functions.md)在頁面上 41) 示範如何使用可巢狀鎖定同步處理更新至整個結構以及其中一個成員。  
  
```  
#include <omp.h>  
typedef struct {int a,b; omp_nest_lock_t lck;} pair;  
  
void incr_a(pair *p, int a)  
{  
    // Called only from incr_pair, no need to lock.  
    p->a += a;  
}  
  
void incr_b(pair *p, int b)  
{  
    // Called both from incr_pair and elsewhere,  
    // so need a nestable lock.  
  
    omp_set_nest_lock(&p->lck);  
    p->b += b;  
    omp_unset_nest_lock(&p->lck);  
}  
  
void incr_pair(pair *p, int a, int b)  
{  
    omp_set_nest_lock(&p->lck);  
    incr_a(p, a);  
    incr_b(p, b);  
    omp_unset_nest_lock(&p->lck);  
}  
  
void f(pair *p)  
{  
    extern int work1(), work2(), work3();  
    #pragma omp parallel sections  
    {  
        #pragma omp section  
            incr_pair(p, work1(), work2());  
        #pragma omp section  
            incr_b(p, work3());  
    }  
}  
```