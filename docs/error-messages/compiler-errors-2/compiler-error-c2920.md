---
title: 編譯器錯誤 C2920 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18a2ccc8809b18d9a28b1fc60f5460dd4272a49c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2920"></a>編譯器錯誤 C2920
重複定義：'class'：類別樣板或泛型已宣告為 'type'  
  
 泛型或樣板類別有多個不相等的宣告。 若要修正此錯誤，請對不同的類型使用不同的名稱，或移除類型名稱的重複定義。  
  
 下列範例會產生 C2920，並顯示如何修正此問題：  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 使用泛型時，也會發生 C2920。  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
```