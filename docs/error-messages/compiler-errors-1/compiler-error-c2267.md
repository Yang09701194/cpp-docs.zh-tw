---
title: "編譯器錯誤 C2267 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2267
dev_langs: C++
helpviewer_keywords: C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c7256335f096648eed0ffc9e15c3acb9f3c5ba1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2267"></a>編譯器錯誤 C2267
'function': 具有區塊範圍的靜態函式不合法  
  
 本機函式宣告`static`。 靜態函式必須具有全域範圍。  
  
 下列範例會產生 C2267:  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```