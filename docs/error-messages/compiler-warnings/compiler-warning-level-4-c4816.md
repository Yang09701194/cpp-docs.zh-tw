---
title: "編譯器警告 （層級 4） C4816 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4816
dev_langs:
- C++
helpviewer_keywords:
- C4816
ms.assetid: 60f730ae-d942-4db9-ab97-41d4a874d8da
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a9df011e42a1c978deac1dbd3050c99b065e3567
ms.contentlocale: zh-tw
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4816"></a>編譯器警告 (層級 4) C4816
'param' : 參數具有大小為零且將被截斷的陣列 (除非物件是透過傳址方式傳遞)  
  
 具有大小為零之陣列的物件參數未透過傳址方式傳遞。 傳遞物件時不會複製陣列。  
  
## <a name="example"></a>範例  
 下列範例會產生 C4816：  
  
```  
// C4816.cpp  
// compile with: /W4  
#include <stdio.h>  
  
extern "C" int printf_s(const char *, ...);  
  
#pragma warning(disable : 4200)  
  
struct S1  
{  
    int i;  
    char cArr[];  
};  
  
void TestErr(S1 s1)   // C4816 param with zero-array   
                      // not passed by reference  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
void TestOk(S1 &s1)  
{  
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);  
}  
  
int main()  
{  
    S1 myS_1 = { 6, 'a', 'b', 'c' };  
    TestErr(myS_1);  
    TestOk(myS_1);  
}  
```
