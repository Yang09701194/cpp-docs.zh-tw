---
title: "編譯器錯誤 C2423 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2423
dev_langs: C++
helpviewer_keywords: C2423
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 33e555f07a0021c059cfff2372a9689c24f89a02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2423"></a>編譯器錯誤 C2423
'number': 不合法的小數位數  
  
 內嵌組譯程式碼會使用 1、 2、 4 或 8 以外的數字來調整暫存器。  
  
 下列範例會產生 C2423:  
  
```  
// C2423.cpp  
// processor: x86  
int main() {  
   _asm {  
      lea EAX, [EAX*3]   // C2423  
      lea EAX, [EAX+EAX*2]   // OK  
   }  
}  
```