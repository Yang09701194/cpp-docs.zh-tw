---
title: "編譯器錯誤 C2574 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2574
dev_langs: C++
helpviewer_keywords: C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31e6b1c7dc2e2a1fcb0a04e284d0251e59ebb8bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2574"></a>編譯器錯誤 C2574
'解構函式': 無法宣告為 static  
  
 解構函式或建構函式都不可以宣告`static`。  
  
 下列範例會產生 C2574:  
  
```  
// C2574.cpp  
// compile with: /c  
class A {  
   virtual static ~A();   // C2574  
   //  try the following line instead  
   // virtual ~A();  
};  
```