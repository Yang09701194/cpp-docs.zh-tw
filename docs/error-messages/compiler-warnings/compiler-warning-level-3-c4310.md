---
title: "編譯器警告 （層級 3） C4310 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4310
dev_langs: C++
helpviewer_keywords: C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 069f7369e635d76668b9def46558a1fa9ccd6d1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4310"></a>編譯器警告 (層級 3) C4310
轉換截斷常數值  
  
 常數值會轉換成較小的類型。 編譯器會執行轉換，會截斷資料。 下列範例會產生 C4310:  
  
```  
// C4310.cpp  
// compile with: /W4  
int main() {  
   long int a;  
   a = (char) 128;   // C4310, use value 0-127 to resolve  
}  
```