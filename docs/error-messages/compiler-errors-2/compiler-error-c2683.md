---
title: 編譯器錯誤 C2683 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2683
dev_langs:
- C++
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35619d93200c2f0e61dbf903f56a70bbe0c48d73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233642"
---
# <a name="compiler-error-c2683"></a>編譯器錯誤 C2683
'cast': 'type' 不是多型類型  
  
 您無法使用[dynamic_cast](../../cpp/dynamic-cast-operator.md)轉換非多型類別 （沒有虛擬函式的類別）。  
  
 您可以使用[static_cast](../../cpp/static-cast-operator.md)執行非多型類型的轉換。 不過，`static_cast`不會執行執行階段檢查。  
  
 下列範例會產生 C2683:  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```