---
title: stable_sort (STL/CLR) |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::stable_sort
dev_langs:
- C++
helpviewer_keywords:
- stable_sort function [STL/CLR]
ms.assetid: c28fc2df-c68b-4923-ac16-9f8edd926fbb
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7b3d3f99e910bb353fbe39174b4a8b3e314214a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="stablesort-stlclr"></a>stable_sort (STL/CLR)
將在指定範圍中的項目排列成非遞減排列，或是依據二元述詞指定的順序準則，並保留對等項目的相對順序。  
  
## <a name="syntax"></a>語法  
  
```  
template<class _BidIt> inline  
    void stable_sort(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void stable_sort(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>備註  
 此函式的行為與 c + + 標準程式庫函式相同`stable_sort`。 如需詳細資訊，請參閱[stable_sort](../standard-library/algorithm-functions.md#stable_sort)。  
  
## <a name="requirements"></a>需求  
 **標頭：** \<演算法 cliext/>  
  
 **命名空間：** cliext  
  
## <a name="see-also"></a>請參閱  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)