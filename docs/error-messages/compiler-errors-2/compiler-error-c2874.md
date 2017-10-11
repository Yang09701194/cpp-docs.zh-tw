---
title: "編譯器錯誤 C2874 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2874
dev_langs:
- C++
helpviewer_keywords:
- C2874
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b5567e796dca8161491e0764523140b516bce886
ms.contentlocale: zh-tw
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2874"></a>編譯器錯誤 C2874
using 宣告造成 'symbol' 的多重宣告  
  
 宣告會造成相同的項目定義了兩次。  
  
 下列範例會產生 C2874:  
  
```  
// C2874.cpp  
namespace Z {  
   int i;  
}  
  
int main() {  
   int i;  
   using Z::i;   // C2874, i already declared  
}  
```
