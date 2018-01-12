---
title: "編譯器警告 （層級 1） C4377 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4377
dev_langs: C++
helpviewer_keywords: C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b2cf61aa35bcfc40a40febb9e066caba6decd682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4377"></a>編譯器警告 (層級 1) C4377
原生型別為私用的預設值;-d1PrivateNativeTypes 已被取代  
  
 在舊版中，組件中的原生型別是公用的預設值，而且內部且未記載的編譯器選項 (**/d1PrivateNativeTypes**) 用來使其私用。  
  
 所有類型，原生和 CLR，現在是私用預設會在組件，因此**/d1PrivateNativeTypes**不再需要。  
  
## <a name="example"></a>範例  
 下列範例會產生 C4377。  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```