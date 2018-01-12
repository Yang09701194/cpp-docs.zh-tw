---
title: "編譯器錯誤 C2689 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2689
dev_langs: C++
helpviewer_keywords: C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6070d4000ada029b1c2735780cb69303c848c05
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2689"></a>編譯器錯誤 C2689
'function': 無法在本機的類別內定義的 friend 函式  
  
 您可以宣告，但本機類別中定義 friend 函式。  
  
 下列範例會產生 C2689:  
  
```  
// C2689.cpp  
// compile with: /c  
void g() {  
   void f2();  
   class X {  
      friend void f2(){}   // C2689  
      friend void f2();   // OK  
   };  
}  
```