---
title: 編譯器錯誤 C2272 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2272
dev_langs:
- C++
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e969e7cadadf1102dadfb8089a847046731b568f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171763"
---
# <a name="compiler-error-c2272"></a>編譯器錯誤 C2272
'function': 靜態成員函式不允許修飾詞  
  
 A`static`宣告成員函式會與記憶體模型規範，例如[const](../../cpp/const-cpp.md)或[volatile](../../cpp/volatile-cpp.md)，而且這類修飾詞不會允許`static`成員函式。  
  
 下列範例會產生 C2272:  
  
```  
// C2272.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1() const volatile;   // C2272  func1 is static  
   void func2() const volatile;   // OK  
};  
```