---
title: bitand | Microsoft Docs
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
- std::bitand
- std.bitand
- bitand
dev_langs: C++
helpviewer_keywords: bitand function
ms.assetid: 279cf9b5-fac1-49de-b329-f1a31b3481fe
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7036915724400938046cdadace2ead63a9adc6d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="bitand"></a>bitand
& 運算子的替代項目。  
  
## <a name="syntax"></a>語法  
  
```  
  
#define bitand &  
  
```  
  
## <a name="remarks"></a>備註  
 巨集會產生運算子  
  
## <a name="example"></a>範例  
  
```  
// iso646_bitand.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 1, b = 2, result;  
  
   result = a & b;  
   cout << result << endl;  
  
   result= a bitand b;  
   cout << result << endl;  
}  
```  
  
```Output  
0  
0  
```  
  
## <a name="requirements"></a>需求  
 **標頭：**\<iso646.h>