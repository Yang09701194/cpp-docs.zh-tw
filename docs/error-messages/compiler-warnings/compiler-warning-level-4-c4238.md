---
title: "編譯器警告 （層級 4） C4238 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4238
dev_langs: C++
helpviewer_keywords: C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e8e52868d97d31243f92307e9bfd158c818c2f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4238"></a>編譯器警告 (層級 4) C4238
使用非標準擴充： 類別右值當做左值  
  
 與舊版的 Visual c + + 中，Microsoft 擴充功能的相容性 (**/Ze**) 可讓您使用的類別類型，如右值的內容中亦隱含或明確地取得其位址。 在某些情況下，如下列範例中，這可能十分危險。  
  
## <a name="example"></a>範例  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 這種用法會導致 ANSI 相容性錯誤 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。