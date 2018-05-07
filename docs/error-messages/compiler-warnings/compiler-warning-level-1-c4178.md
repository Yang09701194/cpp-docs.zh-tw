---
title: 編譯器警告 （層級 1） C4178 |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4178
dev_langs:
- C++
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a85ce7df620485e00d8cef6a83522d82bf496068
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4178"></a>編譯器警告 (層級 1) C4178
對 switch 運算式的類型而言，case 常數 'constant' 太大  
  
 `switch` 運算式中的 case 常數不符合指派給它的類型。  
  
## <a name="example"></a>範例  
  
```  
// C4178.cpp  
// compile with: /W1  
int main()  
{  
    int i;  // maximum size of unsigned long int is 4294967295  
    switch( i )  
    {  
        case 4294967295:   // OK  
            break;  
        case 4294967296:   // C4178  
            break;  
    }  
 }  
```