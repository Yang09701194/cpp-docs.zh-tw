---
title: "_bittestandcomplement，_bittestandcomplement64 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _bittestandcomplement64
- _bittestandcomplement64_cpp
- _bittestandcomplement_cpp
- _bittestandcomplement
dev_langs: C++
helpviewer_keywords:
- btc instruction
- _bittestandcomplement intrinsic
- _bittestandcomplement64 intrinsic
ms.assetid: 53fa12dd-835e-4e5d-baec-a431c8678806
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f25141a548061afbb59164d93214bc05c8dccbbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="bittestandcomplement-bittestandcomplement64"></a>_bittestandcomplement, _bittestandcomplement64
**Microsoft 特定的**  
  
 產生的指令會檢查位址 `b` 的位元 `a`、傳回其目前值，並將位元設為它的補數。  
  
## <a name="syntax"></a>語法  
  
```  
unsigned char _bittestandcomplement(  
   long *a,  
   long b  
);  
unsigned char _bittestandcomplement64(  
   __int64 *a,  
   __int64 b  
);  
```  
  
#### <a name="parameters"></a>參數  
 [in、out] `a`  
 要檢查的記憶體指標。  
  
 [in] `b`  
 要測試的位元位置。  
  
## <a name="return-value"></a>傳回值  
 位於指定位置的位元。  
  
## <a name="requirements"></a>需求  
  
|內建|架構|  
|---------------|------------------|  
|`_bittestandcomplement`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandcomplement64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **標頭檔** \<intrin.h >  
  
## <a name="remarks"></a>備註  
 此常式僅可作為內建常式使用。  
  
## <a name="example"></a>範例  
  
```  
// bittestandcomplement.cpp  
// processor: x86, IPF, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandcomplement)  
#ifdef _M_AMD64  
#pragma intrinsic(_bittestandcomplement64)  
#endif  
  
int main()  
{  
   long i = 1;  
   __int64 i64 = 0x1I64;  
   unsigned char result;  
   printf("Initial value: %d\n", i);  
   printf("Testing bit 1\n");  
   result = _bittestandcomplement(&i, 1);  
   printf("Value changed to %d, Result: %d\n", i, result);  
#ifdef _M_AMD64  
   printf("Testing bit 0\n");  
   result = _bittestandcomplement64(&i64, 0);  
   printf("Value changed to %I64d, Result: %d\n", i64, result);  
#endif  
}  
```  
  
## <a name="sample-output"></a>範例輸出  
  
```  
Initial value: 1  
Testing bit 1  
Value changed to 3, Result: 0  
Testing bit 0  
Value changed to 0, Result: 1  
```  
  
**END Microsoft 特定的**  
  
## <a name="see-also"></a>另請參閱  
 [編譯器內建](../intrinsics/compiler-intrinsics.md)