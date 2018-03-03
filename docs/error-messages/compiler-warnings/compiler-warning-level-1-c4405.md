---
title: "編譯器警告 （層級 1） C4405 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4405
dev_langs:
- C++
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b20bde360df28158ad504739a1de10d90e3ef0cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4405"></a>編譯器警告 (層級 1) C4405
'identifier': 識別項是保留的字  
  
 內嵌組譯碼的保留字做為變數的名稱。 這可能會造成無法預期的結果。 若要修正這個警告，避免保留字為內嵌組譯碼命名的變數。 下列範例會產生 C4405:  
  
```  
// C4405.cpp  
// compile with: /W1  
// processor: x86  
void func1() {  
   int mov = 0, i = 0;  
   _asm {  
      mov mov, 0;   // C4405  
      // instead, try ..  
      // mov i, 0;  
   }  
}  
  
int main() {  
}  
```