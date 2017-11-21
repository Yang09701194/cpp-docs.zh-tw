---
title: "編譯器錯誤 C2104 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2104
dev_langs: C++
helpviewer_keywords: C2104
ms.assetid: 2ea78896-72a6-4901-a1fa-f33ea88ad61b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6b2ac41123a5e8da7fecb99a8959ee97fceb5365
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2104"></a>編譯器錯誤 C2104
在位元欄位上使用 '&' 將被忽略  
  
 您無法取得位元欄位的位址。  
  
 下列範例會產生 C2104:  
  
```  
// C2104.cpp  
struct X {  
   int sb : 1;  
};  
  
int main() {  
   X x;  
   &x.sb;   // C2104   
   x.sb;   // OK  
}  
```