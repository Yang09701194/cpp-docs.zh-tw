---
title: omp_get_nested |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59900f0a1aba1cbc3bacc5cd1d8832e60aebe30b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686876"
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
  
## <a name="see-also"></a>另請參閱  
 [函式](../../../parallel/openmp/reference/openmp-functions.md)