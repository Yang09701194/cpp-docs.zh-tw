---
title: "編譯器錯誤 C2254 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2254
dev_langs: C++
helpviewer_keywords: C2254
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 388d14e4e2d68f2eefc701f6156e27dda4cb9aa0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2254"></a>編譯器錯誤 C2254
'function': 純規範或抽象覆寫規範不允許在 friend 函式  
  
 A`friend`指定為純虛擬函式`virtual`。  
  
 下列範例會產生 C2254:  
  
```  
// C2254.cpp  
// compile with: /c  
class A {  
public:  
   friend void func1() = 0;   // C2254, func1 is friend  
   void virtual func2() = 0;   // OK, pure virtual  
   friend void func3();   // OK, friend not virtual nor pure  
};  
  
void func1() {};  
void func3() {};  
```