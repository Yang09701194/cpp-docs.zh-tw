---
title: "編譯器錯誤 C2279 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2279
dev_langs: C++
helpviewer_keywords: C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e140bc7b9cf417f5c18d77444ac3c90c478829f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2279"></a>編譯器錯誤 C2279
例外狀況規格不能出現在 typedef 宣告  
  
 在下**/Za**，[例外狀況規格](../../cpp/exception-specifications-throw-cpp.md)typedef 宣告中不允許。  
  
 下列範例會產生 C2279:  
  
```  
// C2279.cpp  
// compile with: /Za /c  
typedef int (*xy)() throw(...);   // C2279  
typedef int (*xyz)();   // OK  
```