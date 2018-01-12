---
title: "編譯器警告 （層級 1） C4929 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4929
dev_langs: C++
helpviewer_keywords: C4929
ms.assetid: 95f8ab4f-4468-4caa-acd5-8f4592f03b3c
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38bfd20538db1f11ab2f7f20ab4079e9ed201bc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4929"></a>編譯器警告 (層級 1) C4929
'file': 類型程式庫包含聯集。忽略 'embedded_idl' 限定詞  
  
 Embedded_idl 屬性[#import](../../preprocessor/hash-import-directive-cpp.md)無法套用至類型程式庫因為 union 存在於類型程式庫中。 若要解決這個警告，請勿使用 embedded_idl。  
  
## <a name="example"></a>範例  
 下列範例會定義元件。  
  
```  
// C4929a.cpp  
// compile with: /LD /link /TLBOUT:C4929a.tlb  
#include <objbase.h>  
[module(name="Test")];  
[public, switch_type(short)] typedef union _TD_UNION_TYPE   {  
   [case(24)]  
      float fM;  
   [case(25)]  
      double dMN;  
   [default]  
      int x;  
} TD_UNION_TYPE;  
  
[export, public] typedef struct _TDW_TYPE {  
   [switch_is(sU)] TD_UNION_TYPE w;  
      short sU;  
} TD_TYPE;  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f(TD_TYPE*);  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct C : I {  
   HRESULT f(TD_TYPE*) { return 0; }  
};  
```  
  
## <a name="example"></a>範例  
 下列範例會產生 C4929。  
  
```  
// C4929b.cpp  
// compile with: /c /W1  
#import "C4929a.tlb" embedded_idl   // C4929  
```