---
title: "編譯器警告 （層級 1） C4558 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4558
dev_langs: C++
helpviewer_keywords: C4558
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9e207bb188bdfa31ef1625aa5e1b607823e755e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4558"></a>編譯器警告 (層級 1) C4558
運算元 'value' 的值超出範圍 'lowerbound-upperbound'  
  
 傳遞至組合語言指令的值超出為參數指定的範圍。 值會被截斷。  
  
 下列範例會產生 C4558:  
  
```  
// C4558.cpp  
// compile with: /W1  
// processor: x86  
void asm_test() {  
   __asm pinsrw   mm1, eax, 8;   // C4558  
}  
  
int main() {  
}  
```