---
title: 編譯器警告 （層級 1） C4272 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4272
dev_langs:
- C++
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6de736c3226a9d3377769b65604a458c08e25df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4272"></a>編譯器警告 (層級 1) C4272
'function': __declspec （dllimport）; 標示為匯入函式時，必須指定原生呼叫慣例。  
  
 它是匯出函式標記為錯誤[__clrcall](../../cpp/clrcall.md)呼叫慣例和編譯器發出這個警告，如果您嘗試匯入函式標示為`__clrcall`。  
  
 下列範例會產生 C4272:  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```