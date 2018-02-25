---
title: "treat_as_floating_point 結構 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
dev_langs:
- C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b52d4b5654de177a1a7aed0fa46bc24577b102d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2018
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point 結構
指定是否可將 `Rep` 視為浮點類型。  
  
## <a name="syntax"></a>語法  
  
```  
template <class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## <a name="remarks"></a>備註  
 只有在特製化 `treat_as_floating_point<Rep>` 衍生自 [true_type](../standard-library/type-traits-typedefs.md#true_type) 時，才能將 `Rep` 視為浮點類型。 可以將樣板類別特製化以用於使用者定義類型。  
  
## <a name="requirements"></a>需求  
 **標頭：** \<chrono >  
  
 **命名空間：** std::chrono  
  
## <a name="see-also"></a>請參閱  
 [標頭檔參考](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)

