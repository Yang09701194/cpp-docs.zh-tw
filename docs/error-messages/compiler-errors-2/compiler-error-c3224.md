---
title: "編譯器錯誤 C3224 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3224
dev_langs:
- C++
helpviewer_keywords:
- C3224
ms.assetid: 129be22f-8f3e-4fc6-9ccd-d27d8ef91251
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 383d7a5d4eb77efeaaabbbd2e29c3618f9a7b582
ms.contentlocale: zh-tw
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3224"></a>編譯器錯誤 C3224
'type': 沒有任何多載泛型類別接受 'number' 個泛型類型引數  
  
 編譯器找不到適當的多載。  
  
 下列範例會產生 C3224：  
  
```  
// C3224.cs  
// compile with: /target:library  
public class C<T> {}  
public class C<T,U> {}  
```  
  
 然後，  
  
```  
// C3224b.cpp  
// compile with: /clr  
#using "C3224.dll"  
int main() {  
   C<int,int,int>^ c = gcnew C<int,int,int>();   // C3224  
   C<int,int>^ c2 = gcnew C<int,int>();   // OK  
}  
```
