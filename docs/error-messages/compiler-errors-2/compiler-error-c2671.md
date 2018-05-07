---
title: 編譯器錯誤 C2671 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2671
dev_langs:
- C++
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22812808ce6e159c0f35d9dc2de8e269ecc23cac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2671"></a>編譯器錯誤 C2671
'function': 靜態成員函式沒有 'this' 指標  
  
 A`static`成員函式嘗試存取`this`。  
  
 下列範例會產生 C2671:  
  
```  
// C2671.cpp  
struct S {  
   static S* const func() { return this; }  // C2671  
};  
```