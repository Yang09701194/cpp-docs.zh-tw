---
title: 編譯器錯誤 C2549 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2549
dev_langs:
- C++
helpviewer_keywords:
- C2549
ms.assetid: 29310094-54a3-4605-bc6d-a312a68daf5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21c421448cc821ebca6e999a67aa5adc3fd8ca20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227928"
---
# <a name="compiler-error-c2549"></a>編譯器錯誤 C2549
使用者定義的轉換不能指定傳回型別  
  
 下列範例會產生 C2549:  
  
```  
// C2549.cpp  
// compile with: /c  
class X {  
public:  
   int operator int() { return value; }   // C2549  
  
   // try the following line instead  
   // operator int() { return value; }  
private:  
   int value;  
};  
```