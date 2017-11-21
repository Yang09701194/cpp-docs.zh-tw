---
title: "編譯器錯誤 C2650 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2650
dev_langs: C++
helpviewer_keywords: C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3352820434c8d794d4980a606cb945bd8ecc4a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2650"></a>編譯器錯誤 C2650
'operator': 不可為虛擬函式  
  
 A`new`或`delete`運算子宣告`virtual`。 這些運算子`static`成員函式，且不能是`virtual`。  
  
## <a name="example"></a>範例  
 下列範例會產生 C2650:  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```