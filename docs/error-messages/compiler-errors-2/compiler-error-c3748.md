---
title: "編譯器錯誤 C3748 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3748
dev_langs:
- C++
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 653a732b28f68d201c1ded7a03b5582d3dba11a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3748"></a>編譯器錯誤 C3748
'interface': managed 的介面不能引起事件  
  
 [__Event](../../cpp/event.md)關鍵字不能出現的介面。  
  
 下列範例會產生 C3748:  
  
```  
// C3748.cpp  
__interface I {  
// try the following line instead  
// struct I {  
   __event void f();   // C3748  
};  
  
int main() {  
}  
```