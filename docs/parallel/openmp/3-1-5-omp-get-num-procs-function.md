---
title: "3.1.5 omp_get_num_procs 函式 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: bbfbf17b-0c68-4ba6-a25d-07c36ecb551f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22ae70cd2a98feb610d0a1a3d9d4e073e0875e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="315-ompgetnumprocs-function"></a>3.1.5 omp_get_num_procs 函式
`omp_get_num_procs`函式會傳回所提供的程式時呼叫的函式的處理器數目。 格式如下：  
  
```  
#include <omp.h>  
int omp_get_num_procs(void);  
```