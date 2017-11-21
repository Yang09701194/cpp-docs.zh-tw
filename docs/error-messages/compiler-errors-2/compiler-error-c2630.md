---
title: "編譯器錯誤 C2630 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2630
dev_langs: C++
helpviewer_keywords: C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a983ed18961374d999ad0a19e22be9a5316ed4c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2630"></a>編譯器錯誤 C2630
' symbol' 應該以逗號分隔的清單中找到  
  
 符號會出現在內容需要逗號。  
  
 下列範例會產生 C2630:  
  
```  
// C2630.cpp  
// compile with: /c  
struct D {  
   D(int);  
};  
  
struct E {  
   E(int);  
};  
  
class C : public D, public E {  
   C();  
};  
  
C::C() : D(0) ; E(0) { }   // C2630  
C::C() : D(0), E(0) {}   // OK  
```