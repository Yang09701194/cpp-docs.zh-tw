---
title: "編譯器錯誤 C2450 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2450
dev_langs: C++
helpviewer_keywords: C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9168071c02140b1a334c1c31acda08edb82b4bec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2450"></a>編譯器錯誤 C2450
類型 'type' 的 switch 運算式不合法  
  
 `switch`運算式評估為無效的類型。 它必須評估為整數類型或類別類型為整數型別模稜兩可的轉換。 如果評估為使用者定義型別，您必須提供轉換運算子。  
  
 下列範例會產生 C2450:  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```