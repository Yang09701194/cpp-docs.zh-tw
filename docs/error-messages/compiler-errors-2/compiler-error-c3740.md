---
title: "編譯器錯誤 C3740 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3740
dev_langs: C++
helpviewer_keywords: C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1466945e3b6647bedccd65e899bb3eb78ac28de1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3740"></a>編譯器錯誤 C3740
無法為來源或接收的事件範本  
  
 樣板類別或結構不能包含[事件](../../cpp/event-handling.md)。  
  
 下列範例會產生 C3740:  
  
```  
// C3740.cpp  
template <typename T>   // Delete the template specification  
struct E {  
   __event void f();   // C3740  
};  
  
int main() {  
}  
```