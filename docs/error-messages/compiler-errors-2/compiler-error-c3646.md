---
title: 編譯器錯誤 C3646 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad0a7f16b54d2a06586bdb4c26c87dbcf9ae7b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3646"></a>編譯器錯誤 C3646
'specifier': 未知的覆寫規範  
  
 編譯器發現語彙基元中的位置，其中預期找到覆寫規範，但編譯器無法辨識的 token。  
  
 如需詳細資訊，請參閱[覆寫規範](../../windows/override-specifiers-cpp-component-extensions.md)。  
  
 下列範例會產生 C3646:  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```