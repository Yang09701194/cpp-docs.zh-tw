---
title: 排程 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- schedule
dev_langs:
- C++
helpviewer_keywords:
- schedule OpenMP clause
ms.assetid: 286f1fc3-6598-4837-b4c8-8b1fa3193965
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95811d262dc674a75ded45c621212c5f4c506213
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068405"
---
# <a name="schedule"></a>排程
適用於[針對](../../../parallel/openmp/reference/for-openmp.md)指示詞。  
  
## <a name="syntax"></a>語法  
  
```  
schedule(type[,size])  
```  
  
#### <a name="parameters"></a>參數  
*type*<br/>
排程的類型：  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
*size*<br/>
（選擇性）指定反覆項目的大小。 `size` 必須是整數。 不是有效的 when`type`是`runtime`。  
  
## <a name="remarks"></a>備註  
 如需詳細資訊，請參閱 < [2.4.1 for 建構](../../../parallel/openmp/2-4-1-for-construct.md)。  
  
## <a name="example"></a>範例  
  
```cpp  
// omp_schedule.cpp  
// compile with: /openmp   
#include <windows.h>  
#include <stdio.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define STATIC_CHUNK 5  
#define DYNAMIC_CHUNK 5  
#define NUM_LOOPS 20  
#define SLEEP_EVERY_N 3  
  
int main( )   
{  
    int nStatic1[NUM_LOOPS],   
        nStaticN[NUM_LOOPS];  
    int nDynamic1[NUM_LOOPS],   
        nDynamicN[NUM_LOOPS];  
    int nGuided[NUM_LOOPS];  
  
    omp_set_num_threads(NUM_THREADS);  
  
    #pragma omp parallel  
    {  
        #pragma omp for schedule(static, 1)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nStatic1[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(static, STATIC_CHUNK)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nStaticN[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(dynamic, 1)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nDynamic1[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nDynamicN[i] = omp_get_thread_num( );  
        }  
  
        #pragma omp for schedule(guided)  
        for (int i = 0 ; i < NUM_LOOPS ; ++i)   
        {  
            if ((i % SLEEP_EVERY_N) == 0)   
                Sleep(0);  
            nGuided[i] = omp_get_thread_num( );  
        }  
    }  
  
    printf_s("------------------------------------------------\n");  
    printf_s("| static | static | dynamic | dynamic | guided |\n");  
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",  
             STATIC_CHUNK, DYNAMIC_CHUNK);  
    printf_s("------------------------------------------------\n");  
  
    for (int i=0; i<NUM_LOOPS; ++i)   
    {  
        printf_s("|    %d   |    %d   |    %d    |    %d    |"  
                 "    %d   |\n",  
                 nStatic1[i], nStaticN[i],  
                 nDynamic1[i], nDynamicN[i], nGuided[i]);  
    }  
  
    printf_s("------------------------------------------------\n");  
}  
```  
  
```Output  
------------------------------------------------  
| static | static | dynamic | dynamic | guided |  
|    1   |    5   |    1    |    5    |        |  
------------------------------------------------  
|    0   |    0   |    0    |    2    |    1   |  
|    1   |    0   |    3    |    2    |    1   |  
|    2   |    0   |    3    |    2    |    1   |  
|    3   |    0   |    3    |    2    |    1   |  
|    0   |    0   |    2    |    2    |    1   |  
|    1   |    1   |    2    |    3    |    3   |  
|    2   |    1   |    2    |    3    |    3   |  
|    3   |    1   |    0    |    3    |    3   |  
|    0   |    1   |    0    |    3    |    3   |  
|    1   |    1   |    0    |    3    |    2   |  
|    2   |    2   |    1    |    0    |    2   |  
|    3   |    2   |    1    |    0    |    2   |  
|    0   |    2   |    1    |    0    |    3   |  
|    1   |    2   |    2    |    0    |    3   |  
|    2   |    2   |    2    |    0    |    0   |  
|    3   |    3   |    2    |    1    |    0   |  
|    0   |    3   |    3    |    1    |    1   |  
|    1   |    3   |    3    |    1    |    1   |  
|    2   |    3   |    3    |    1    |    1   |  
|    3   |    3   |    0    |    1    |    3   |  
------------------------------------------------  
  
```  
  
## <a name="see-also"></a>另請參閱  
 [子句](../../../parallel/openmp/reference/openmp-clauses.md)