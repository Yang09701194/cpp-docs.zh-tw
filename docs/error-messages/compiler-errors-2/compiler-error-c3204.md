---
title: "編譯器錯誤 C3204 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3204
dev_langs:
- C++
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: ea8cfac81b7c4a7856543c00e45ed3c067a4d8cf
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3204"></a>編譯器錯誤 C3204
無法從 catch 區塊呼叫 '_alloca'  
  
 當您使用的呼叫時，就會發生此錯誤[_alloca](../../c-runtime-library/reference/alloca.md)從 catch 區塊內。  
  
## <a name="example"></a>範例  
 下列範例會產生 C3204：  
  
```  
// C3204.cpp  
// compile with: /EHsc  
#include <malloc.h>  
  
void ShowError(void)  
{  
   try  
   {  
   }  
   catch(...)  
   {  
      _alloca(1);   // C3204  
   }  
}  
```
