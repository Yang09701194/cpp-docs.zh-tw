---
title: "編譯器錯誤 C3745 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3745
dev_langs:
- C++
helpviewer_keywords:
- C3745
ms.assetid: 1e64aec5-7e53-47e5-bc7d-3905230cfc66
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 330e9c62e2235e1f352b64d1f236423d6786cc1d
ms.contentlocale: zh-tw
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3745"></a>編譯器錯誤 C3745
'function': 只有事件可以 'raised'  
  
 只有函式以定義[__event](../../cpp/event.md)關鍵字可以傳遞至[__raise](../../cpp/raise.md)關鍵字。  
  
 下列範例會產生 C3745:  
  
```  
// C3745.cpp  
struct E {  
   __event void func();  
   void func(int) {  
   }  
  
   void func2() {  
   }  
  
   void bar() {  
      __raise func();  
      __raise func(1);   // C3745  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func();  
   __raise e.func(1);   // C3745  
   __raise e.func2();   // C3745  
}  
```
