---
title: "編譯器錯誤 C3417 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3417
dev_langs:
- C++
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e25adc1b699998235c1cfa16edbb50c2b774f983
ms.contentlocale: zh-tw
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3417"></a>編譯器錯誤 C3417
'member': 實值類型不能包含使用者定義的特殊成員函式  
  
 實值類型不能包含等預設執行個體建構函式、 解構函式或複製建構函式的函式。  
  
 下列範例會產生 C3517:  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```
