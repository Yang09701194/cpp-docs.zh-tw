---
title: xor_eq | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- std.xor_eq
- xor_eq
- std::xor_eq
dev_langs: C++
helpviewer_keywords: xor_eq function
ms.assetid: eca4b6b4-b77a-4d44-a09a-5a7e69fdb56c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56a07d8ba30981e4a8e5051ed723ce0967cd3627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="xoreq"></a>xor_eq
^= 運算子的替代項目。  
  
## <a name="syntax"></a>語法  
  
```  
  
#define xor_eq ^=  
  
```  
  
## <a name="remarks"></a>備註  
 巨集會產生 ^= 運算子。  
  
## <a name="example"></a>範例  
  
```  
// iso646_xor_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 3, b = 2, result;  
  
   result= a ^= b;  
   cout << result << endl;  
  
   a = 3;  
   b = 2;  
  
   result= a xor_eq b;  
   cout << result << endl;  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="requirements"></a>需求  
 **標頭：**\<iso646.h>