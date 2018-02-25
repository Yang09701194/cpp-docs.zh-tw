---
title: "omp_get_nested |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df6a3fafdb749031ae5e55a58e1e26ccad76985c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetnested"></a>omp_get_nested
傳回值，指出是否已啟用巢狀平行處理原則。  
  
## <a name="syntax"></a>語法  
  
```  
int omp_get_nested( );  
```  
  
## <a name="return-value"></a>傳回值  
 如果是非零值，已啟用巢狀平行處理原則。  
  
## <a name="remarks"></a>備註  
 指定巢狀平行處理原則[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)和[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)。  
  
 如需詳細資訊，請參閱[3.1.10 omp_get_nested 函式](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)。  
  
## <a name="example"></a>範例  
 請參閱[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)的使用範例`omp_get_nested`。  
  
## <a name="see-also"></a>請參閱  
 [函式](../../../parallel/openmp/reference/openmp-functions.md)